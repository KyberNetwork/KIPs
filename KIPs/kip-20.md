---
kip: 19
title: Calibrating KyberDAO Governance Parameters
status: Active
type: Updating DAO Configuration
authors: Kyber Network team
created: 2022-05-06 test1
---

```
campaign_type: binary
executor: long timelock executor
voting_power: current staked voting power
execution: Calibrate KyberDAO Governance Parameters
start_timestamp: 1650351600 (Tuesday, 19 April 2022 07:00:00 UTC)
end_timestamp: 1650956400 (Tuesday, 26 April 2022 07:00:00 UTC)
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 150000000000000000 (15%)

```

## Summary

42M KNC (Kyber Network Crystal) tokens were minted after KIP-8 in 2021 and managed by KyberDAO as a Kyber Ecosystem Growth Fund for the purpose of increasing Kyber’s liquidity and adoption through various activities through 2022, including liquidity mining and ecosystem collaborations.

There are approximately 23,747,562 KNC remaining (~$83M at $3.50 per KNC) in the fund after key liquidity mining campaigns on Ethereum, Polygon, BNB Chain, Avalanche, and BitTorrent, as well as those with partners such as xToken, xDollar, Jarvis Network, DeFi Warrior, Creator, Elpis Battle, GemUni, StepHero, APEIN, DYP Protocol, Pegaxy, Sipher, Unbound Finance, Evrynet, and Benqi.

Now that our KyberSwap DEX aggregator has been deployed on 11 chains (many more in the pipeline), further boosted by an upcoming launch of Elastic-type liquidity pools that offers even greater capital efficiency for liquidity providers, we propose that KyberDAO utilize the remaining KNC for even more growth activities on KyberSwap, instead of simply burning the KNC.

Proposed Use Cases for Remaining KNC Funds

- Trading and Liquidity Growth | ~62%
- Milestone-based Ecosystem Grants | ~22%
- 5-year Anniversary Marketing Activities | ~14%
- Bonus rewards for KyberDAO staking and voting | ~2%

### Motivation
Our past trading and liquidity bootstrapping activities on KyberSwap have led to some degree of success. Since the launch of the new KyberSwap version last year, thousands of liquidity providers have earned approximately $8M in trading fees and KNC voters $1M in rewards. Total value locked (TVL) in our pools reached $140M recently and the value of KNC staked on KyberDAO is worth $210M. This progress has partly been reflected in the value of KNC, which has increased by 300+% since Jan 1, 2022. In addition, we now have almost 10,000 KNC holders that are part of the Kyber community and ecosystem, as well as close ties with many top DeFi and GameFi projects.

In order to continue this positive growth, we would like to further allocate and utilize the KNC in our ecosystem growth fund. Most popular DEXes carry out some form of liquidity mining or incentive program to attract users, so it is necessary for KyberSwap to do the same to stay competitive.

KyberSwap already has several technical advantages over other DEXes in terms of best rates through DEX aggregation and capital-efficient liquidity pools, and KNC incentives would further amplify our DeFi mindshare and user acquisition on all supported chains.

### Proposed Changes

Proposed Allocation for Remaining KNC in the Fund
Below we present an overview of the KNC allocation for the different initiatives; namely trade & liquidity mining (further split into incentives per chain), milestone-based grants, marketing activities, and bonus KyberDAO voter rewards. Note that this KNC in our ecosystem growth fund is managed by KyberDAO and is separate from the Kyber team’s treasury.

Total KNC remaining in the fund: 23,747,562 KNC

1. For Trading and Liquidity Growth

KNC Amount: 14,567,562 KNC (~62%)

We plan to continue working with the foundation/core team of each chain to devise strategic trading and liquidity mining initiatives that would bring tens of thousands more users to KyberSwap. To complement this, we have been optimizing our pools and liquidity mining strategy to attract more sustainable, long-term liquidity provision instead of just ‘hot money’ mercenary capital.

We propose that the bulk of the remaining KNC (~62%) be used for activities related to trading and liquidity growth. Some of this KNC would also be used for seeding initial pools, bridging KNC into different chains (supporting KNC on cross-chain bridges), and other ad hoc activities.

The proposed allocation below is based on a few factors including on-chain volume, liquidity, and Dapp activity, and the amount of incentives already allocated before this phase. Allocation % might change given the dynamic nature of each chain, subject to community feedback and future KyberDAO votes.

Chain	% Allocation from Trading & Liquidity Growth funds
Ethereum	5%
Polygon	9%
BNB	9%
Avalanche	2%
Fantom	10%
Arbitrum	8%
Aurora	8.5%
Cronos	6%
Oasis	4%
BitTorrent Chain	1%
Velas	0.5%
Future liquidity mining on other chains and ad hoc activities	37%
Within each chain that is currently supported on KyberSwap, we have identified certain token pairs as high priority due to their trading volume and popularity. Stablecoin and correlated pairs are especially critical, since KyberSwap’s high capital efficiency is best observed on such pairs. We plan to seed and use KNC to incentivize these liquidity pools, among others.


### New KyberDAO Configurations

#### DAO Operator

There is a 5/9 multisig with the role of a DAO operator that assists with operational tasks and ensuring the integrity of the DAO. They are a mix of Kyber team members and founders of external DeFi projects with no direct affiliation to Kyber.

daoOperator address (multisig): 0xe6a7338cba0a1070adfb22c07115299605454713

1. Loi - Kyber (representing the Kyber founding team) 0xc8a1dab586dee8a30cb88c87b8a3614e0a391fc5

2. Victor - Kyber (representing developers)  
   0x8180a5ca4e3b94045e05a9313777955f7518d757

3. Mike - Kyber (representing the smart contracts team) 0xBE2F0354D970265BFc36D383af77F72736b81B54

4. Sunny - Krystal (representing DeFi Dapps) 0xdE6BBD964b9D0148d46FE6e2E9Cf72B020ADc519

5. John - Signum Capital (representing VCs and KNC holders) 0x8eC1455f17d9E021Acc8a30F23461DEdff5018Ba

6. Hunter/DeFi Dude - (representing the DeFi Community) 0x499b2408A0a6B43fea49Df79d98246f88ECC8465

7. 0x7a33 - Anonymous (representing professional market makers) 0xffF96a443aB8e8eFF4621c1Aa02Bbd90aD39DA57

8. Michael - xToken (representing staking pools/Dapps) 0x2171861D0943b50d375a800E6c6ea061758C8eB4

9. Michael - Unagii (representing staking pools/Dapps) 0x6c7C332a090c8D2085857cf3220eA01C6d45a723

#### New Configurations

| Subject    |      Actors      |                                                            Permissions | Proposed Contract      |
| ---------- | :--------------: | ---------------------------------------------------------------------: | ---------------------- |
| KNC Token  |      Miner       |                                                               Mint KNC | Long Timelock Executor |
|            |   Proxy Admin    |                                              Change KNC implementation | Long Timelock Executor |
|            | Withdrawal Admin | Withdraw tokens from the contract due to accidental transfer of tokens | 3/5 Multisig           |
| Governance |      Admin       |                     Authorize and deauthorize executors and strategies | Long Timelock Executor |
|            |  Executor Admin  |                       Queue, cancel, and execute proposal transactions | Governance Contract    |
|            |   DAO Operator   |                                            Create and cancel proposals | 5/9 Multisig           |

#### Timelock Executor Configurations

| Properties         |                                                          Definition                                                          | Short Timelock | Long Timelock |
| ------------------ | :--------------------------------------------------------------------------------------------------------------------------: | -------------: | ------------- |
| Delay              |                                              Waiting time to execute proposals                                               |       12 hours | 1 week        |
| Grace period       |                                         Proposal execution period before it expires                                          |         4 days | 7 days        |
| Min delay          |                                         Minimum time in the range of a delay config                                          |         1 hour | 24 hours      |
| Max delay          |                                         Maximum time in the range of a delay config                                          |       24 hours | 2 weeks       |
| Min vote duration  |                                            Minimum voting duration of a proposal                                             |         4 days | 7 days        |
| Max voting options |                                           Maximum number of options in a proposal                                            |              8 | 8             |
| Vote differential  | The difference needed between the votes behind the For/Against options (percentage of Total KNC supply in the market needed) |          0.01% | 15%           |
| Min quorum         |                      Minimum percentage of Total KNC supply in the market needed for the winning option                      |             4% | 20%           |

The new Timelock Executor has been deployed here: 0x7d4d05B1a1E5775a9C6ca248ABBE629B52C1D9D9 with corresponding configurations.

### Other Important Considerations

1. It is possible for the current governance mechanisms and permissions proposed for the new KyberDAO to be changed in the future, or new suitable strategies and mechanisms from the community to be added, subject to a proposal and vote by the new KyberDAO itself.

2. The Kyber core team is the current network maintainer and one of the main actors/admin in the KyberDAO, helping to execute critical tasks to maintain and grow the network. But the team alone does not have the power to implement major changes to the KyberDAO and the protocols in the network. Any contract alteration must be first decided by a KyberDAO vote.

## Conclusion

Kyber is on a path of progressive decentralization. Although our current governance framework is largely based on Aave (considered best practice), we are always open to community feedback and will optimize it when deemed suitable. This KIP will help KyberDAO ensure greater decentralization and diversity, while strengthening its ability to withstand attacks on its governance process by malicious actors.