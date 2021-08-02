---
kip: 11
title: Fee liquidation framework and reward distribution algorithm
status: Active
type: Configuration
authors: Kyber Network team
created: 2021-07-19
---

```
executor: long timelock executor
voting_power: current staked voting power
execution: [Waiting for audit to finalize]
start_timestamp: [Waiting for audit to finalize]
end_timestamp: [Waiting for audit to finalize]
```

## Summary

KIP-11 proposes a fee liquidation framework and an algorithm to calculate reward distribution to KyberDAO voters. Currently, collected fees from protocols in Kyber's liquidity hub are being accumulated and will only be distributed after this framework has been finalised and approved.
1. The fee liquidation framework allows the DAO to whitelist one or more liquidators. The liquidators can convert the fee to the whitelisted reward token and distribute it to voters.
2. The fee liquidation framework allows the DAO to whitelist one or more price oracles to be used as a sanity check to ensure liquidators are distributing the expected amount of reward tokens.
3. The fee liquidation framework allows the DAO to configure the schedule of the liquidation process; when the process opens so liquidators can start, when it closes and when it open agains.
4. The fee liquidation framework allows the DAO to give a premium to liquidators to incentivize them to spend gas for the process. The premiums can be different for different liquidators.
5. The fee liquidation framework allows the DAO to whitelist a trusted operator to pause/unpause the liquidation process during abnormal cases.
6. The reward distribution algorithm is designed to calculate stakers' reward share from epoch N to before epoch M (time period may vary; depends on the two epochs).
7. The algorithm will sum up all of a staker's voting points for all proposals created within that time period regardless of proposal cancellation.
8. The algorithm will use stakers' reward share to calculate a merkle root and the full dataset will be published to IPFS.

## Motivation

KyberDAO v2 has been deployed and successfully placed a general DAO framework for the Kyber community to govern different liquidity protocols in the liquidity hub including KyberDMM, bridge reserves and FPR reserves. However, the DAO is currently collecting fees from these protocols without a process to distribute them to DAO stakers/voters. 

We propose a general framework to allow the DAO to convert collected fees (which is in the form of many different types of tokens including LP tokens) to one or a few preferred reward tokens to be distributed to voters. This process is called **Fee Liquidation**.

We also propose an algorithm to track and calculate a staker's share of the reward pool in order to generate the merkle root to submit to the DAO.

## Fee Liquidation Framework

### Terminology
1. **Fee Token** - Token the DAO collects from all of its different liquidity protocols.
2. **Reward token** - Token the DAO intends to convert all fee tokens to, prior to distribution to voters. Reward token should be a high liquidity asset such as ETH, KNC or stable assets.
3. **Liquidation contract** - A smart contract the DAO whitelists as a liquidation strategy.
4. **Liquidator** - A smart contract that handles the liquidation.
5. **Price oracle** - A smart contract that calculates the expected amount of reward tokens in order to do a sanity check on what a liquidator will distribute in a liquidation.
6. **Liquidation type** - Liquidation may come in different forms. In this framework, we support 2 types of liquidations (more details below).

### Liquidation Flow
![liquidation flow](https://i.imgur.com/3B1nLpr.png)

The diagram above describes how a liquidation process will happen.
1. To conduct the liquidation, a transaction is done by either the Kyber core team, a manager, or anyone with the *liquidator* contract. 
The function is `function liquidate(
    ILiquidationPriceOracleBase oracle,
    IERC20Ext[] calldata sources,
    uint256[] calldata amounts,
    address payable recipient,
    IERC20Ext dest,
    bytes calldata oracleHint,
    bytes calldata txData)` where `oracle` is one of the whitelisted price oracles, `sources` are a list of fee tokens, `amounts` are the amount of fee tokens to liquidate, `recipient` is where the fee tokens should be sent to, `dest` is a whitelisted reward token the liquidation will convert fees to, `oracleHint` is the additional data to pass to the oracle to help it calculate the expected reward token amount, `txData` is additional data to pass to the `recipient.liquidationCallback` function to perform additional operations a liquidator might need.
2. The *liquidation contract* then calls the `oracle` in order to calculate the expected reward token amounts.
3. The *liquidation contract* will call a function on the `treasury contract` to withdraw fee tokens to recipient.
4. The *liquidator* transfers the reward token as in `dest` to the *liquidation contract*.
5. The *liquidation contract* checks the received reward token amounts against the expected amounts calculated by the oracle. If the received amounts are higher or equal to the expected amounts, it transfers the reward tokens to the `reward` component and completes the liquidation process.

### Price oracles
Price oracles are very important components of the liquidation process. They play the role of a guardian to prevent the fee tokens in the treasury from being converted at an unreasonably low rate. They also have to support different fee tokens including LP tokens (receipt tokens representing your liquidity position) that need some additional logic in order to evaluate the underlying tokens they hold. For KIP-11, we propose the very first *price oracle* that uses ChainLink price oracles to support LP token fee liquidation and configurable premium (discount) for integrations.

#### KyberDmmChainLinkPriceOracle
In this price oracle, we support 2 different liquidation types:
1. **Liquidate DMM LP tokens** - The price oracle contract will look up the underlying token prices of the LP tokens on ChainLink to calculate the minimum expected amounts. Both underlying tokens of the LP token need to have ChainLink oracle proxies configured to be a valid liquidation.
2. **Liquidate normal tokens** - The price of the tokens on ChainLink will be used to calculate the minimum expected amounts.
When a liquidation takes place, it specifies the liquidation type via `oracleHint` param and this oracle will calculate the minimum amounts of reward tokens accordingly. This oracle also incentivizes integrations to liquidate by giving premium per whitelisted liquidator.

The ChainLink proxies are configurable by an operator. The operator can be one of the DAO proposal executors or a normal wallet. For KIP-11, we propose to start with giving the DAO operator the authority to swiftly configure necessary premium and ChainLink proxies to help ensure a smooth operation of the DAO.

On the other hand, the DAO's short executor is proposed to be this price oracle admin in order to configure premium settings.

### Schedule
There should be no restriction on when the liquidation process can start, however, to allow more possibilities in the future, the Liquidation process is designed to have a *LiquidationSchedule*, which includes:
1. **Start time** - the time that the first liquidation process will happen.
2. **Repeated Period** - the time period between between the start of the current liquidation process and the start of the next.
3. **Duration** - the duration of each liquidation period.

For example:
Starting from 3pm June 14, 2021 UTC+0, for every week, the liquidation process will be enabled for 2 days. The schedule data should look like this:
*Start time:* June 14, 2021, 3pm UTC.
*Repeated Period:* 1 week.
*Duration:* 2 days.

**Note:** To allow the liquidation process to always be open, we can just set *Repeated Period* = *Duration*.

**Note:** If the liquidation operator pauses the liquidation contract, the *LiquidationSchedule* will have no effect until it is unpaused.

### KyberNetwork liquidator
We propose a simple decentralized liquidator smart contract that takes fee tokens and converts them to any preferred reward tokens using Kyber Network, which already aggregates many different liquidity sources such as KyberDMM, FPR reserves, Uniswap, Sushiswap and Curve. 

For KIP-11, Kyber's native token **KNC is proposed as the whitelisted reward token**, after careful consideration of community feedback in our [governance forum](https://gov.kyber.org/t/discuss-new-kyberdao-fee-liquidation-system/247).

### Default settings
1. Liquidation Schedule
1.1 Start: //TODO
1.2 Repeated period: 1 week
1.3 Duration: 1 day
2. Liquidation operator: Dao Operator at 0xe6a7338cba0a1070adfb22c07115299605454713
3. Whitelisted reward tokens: KNC
4. Oracle operator: Dao Operator at 0xe6a7338cba0a1070adfb22c07115299605454713
5. Premium for KyberNetwork liquidator: 0 bps

### Implementation
The implementation can be found [here](https://github.com/KyberNetwork/dao_sc/tree/mike_liquidation_strategy/contracts/treasury).

## Reward distribution algorithm
### Backgound

As [KIP-7](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-7.md) states, the KyberDAO architecture consists of a Reward component which is supposed to distribute reward tokens to voters. That component currently allows the DAO operator to upload the merkle root of a merkle tree that specifies a mapping of each user to their total accumulated rewards, across every token for which rewards are distributed. The reward amounts are tracked and generated off-chain by the Kyber team. For KIP-11, we propose an algorithm to calculate voters' share of the reward pool which is needed to build the merkle tree.

### Algorithm pseudocode
```
// calculate stakers' share from epoch N to before epoch M
// params:
//   - N, M
// returns:
//   - map[staker_address => share]

GOVERNANCE_CONTRACT = 0x7ec8fcc26be7e9e85b57e73083e5fe0550d8a7fe
VOTE_EVENT = event VoteEmitted(
  uint256 indexed proposalId,
  address indexed voter,
  uint32 indexed voteOptions,
  uint224 votingPower
)
BINARY_PROPOSAL_EVENT = event BinaryProposalCreated(
  uint256 proposalId,
  address indexed creator,
  IExecutorWithTimelock indexed executor,
  IVotingPowerStrategy indexed strategy,
  address[] targets,
  uint256[] weiValues,
  string[] signatures,
  bytes[] calldatas,
  bool[] withDelegatecalls,
  uint256 startTime,
  uint256 endTime,
  string link,
  uint256 maxVotingPower
)
GENERAL_PROPOSAL_EVENT = event GenericProposalCreated(
  uint256 proposalId,
  address indexed creator,
  IExecutorWithTimelock indexed executor,
  IVotingPowerStrategy indexed strategy,
  string[] options,
  uint256 startTime,
  uint256 endTime,
  string link,
  uint256 maxVotingPower
)

func calculate_share(N, M):
  
  blockN = get_beginning_block_of_epoch(N)
  blockM = get_beginning_block_of_epoch(M)
  
  // getting a list of proposal IDs
  proposalIDs = query_logevent(
    event_signature: BINARY_PROPOSAL_EVENT | GENERAL_PROPOSAL_EVENT,
    from_block: blockN,
    to_block: blockM-1,
    at_contract: GOVERNANCE_CONTRACT,
  )

  // getting a list of voter addresses
  voters = query_logevent(
    event_signature: VOTE_EVENT,
    from_block: blockN,
    to_block: blockM-1,
    at_contract: GOVERNANCE_CONTRACT,
  )

  total_voting_point = 0
  voter_data = map[voter_address => float64]
  for id in proposalIDs:
    for voter in voters:
      _, voting_point = GOVERNANCE_CONTRACT.getVoteOnProposal(id, voter)
      voter_data[voter] += voting_point
      total_voting_point += voting_point

  // calculate actual share
  for voter in voters:
    voter_data[voter] = voter_data[voter] / total_voting_point

  return voter_data
```
This map of reward share data will be used to build the merkle tree and its root will be submited to the RewardDistributor contract at 0x5ec0dcf4f6f55f28550c70b854082993fdc0d3b2.

The merkle tree construction is documented [here](https://docs.google.com/document/d/1mLG3muhM9hQMafdznqrHRbDRIT2HEuQ-MZZY_jnOEtw/edit?usp=sharing) as part of the KyberDAO design and specifications.

## Onchain execution

1. Remove/unauthorize the current liquidation strategy **0x8694103eD4927D389F63213619708e550e9631D7** from Treasury pool **0x5EC0DcF4f6F55f28550c70B854082993fdc0D3B2**
2. Authorize new liquidation strategy in Treasury pool: [Waiting for audit to finalize]

## Conclusion
This fee liquidation framework will apply to all new liquidity protocols added to Kyber’s liquidity hub. Each protocol sends a portion of their fees to KyberDAO and fees will be converted to the whitelisted reward token (KNC) by default, before being distributed to voters. As more protocols are created and added to Kyber’s liquidity hub, more fees will flow to KyberDAO and voters will receive more KNC rewards. Voters can easily stake the KNC on KyberDAO again for more voting power and rewards, without the hassle of making another swap.
