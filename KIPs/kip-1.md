---
kip: 1
title: Kyber Dao concepts and terminologies 
status: Active
type: Information
author: Kyber Network team
created: 2020-07-10
---

In this very first KIP, we formally define the core concepts and terminologies of Kyber DAO to set a common ground for Kyber community. The definitions here will be used as the truth (not assumption) in every discussion of the DAO.

## Kyber Market
A **Kyber Market** contains of *Proxy contracts, Network contract, Storage contract, MatchingEngine contract a FeeHandler contract and 
reserves*. All reserves price their listed tokens in a particular **currency**. If a market is with currency A, we call it **Kyber A Market**, the currrent Kyber Network is called **Kyber ETH Market**. The currency can be called `quote_token` interchangeably.

## Epoch
An epoch is a continuous range of Ethereum blocks. Each epoch is assigned to a number starting from 0. *Epoch 0 is called E0, Epoch 1 is called E1 and so on*. Every epoch lasts exactly 14 days (1209600 seconds) based on block's timestamp except E0 which started at this [transaction](https://etherscan.io/tx/0x9e2390fc23c8b7a6c603b9f4919c3e1c7b7187ff3dbb1062040434577a5fd028). E1 starts at 07:07:07 14th July, 2020 UTC+0.

Each epoch has maximum 1 Fee Campaign and 1 BRR Campaign, it can have many General Campaigns and less than 10 campaigns in total for 1 epoch.

## Network fee
Network fee is taken in every trade and sent to the FeeHandler contract of the market. Each market will have network fee in its currency. For example, Kyber ETH market will take the fee in ETH, Kyber USDT market will take the fee in USDT. The amount of the network fee is decided by the DAO via Fee Campaigns which happen each 3 months.

The network fee percentage is decided by the DAO contract via Fee Campaigns, or can be decided by the DAO via General Campaigns. If the network fee percentage is decided via a General Campaigns, the Dao Operator needs to manually configure it.

*Note: In the Kyber ETH market, the fee percentage is strictly decided via Fee Campaigns.*

Network fee is taken in the following rules:
- The amount of network fee is based on the equivalent trade size in `quote_token` and the `network_fee_percentage`.
- If a trade goes to a reserve which is not accounted for the fee, no fee will be taken for the volume that reserve handled.
- If a trade is token to token, network_fee will be taken twice, one for token to quote_token part and one for quote_token to token part.
- The collected fee is sent to its own market's FeeHandler contract.
- The collected fee will be broken into 3 parts: Burn, Reward, and Rebate.
- The collected fee is not under control of the Network admin nor Dao Operator.

### Feeless Reserve, Feeless Volume
Every reserve comes with its own reserve type. Each reserve type has its **fee flag** to determine if the trade going to that reserve is going to pay network fee or not. If a reserve type has its **fee flag** set to False, all of the reserves with that type are called **feeless reserve** and the volume it handled is called **feeless volume**.

## Reward
Reward is part of the fee that the FeeHanlder of each market collects to pay for the Dao's voters. Reward is accumulated in each epoch independently and only be claimable after an epoch ends which means if E10 ended, Dao's voters can claim their reward for E10 whenever they want, in E11, E12 and so forth.

The reward of a voter is proportional to how many voting points he/she made in the epoch. 

Whenever a voter votes for a voting campaign, he/she will get an amount of voting point equals to the amount of KNC he/she staked in the previous epoch. If he/she voted for the campaign and decided to vote again, his/her vote will be recorded/acknowledged for the vote option, however, his/her voting points stays the same. In the other words, a voter can only get voting points once for a campaign.

Whenever a voter withdraws his/her staked KNC, he/she's voting points of the current epoch will be deducted proportionally.

Note: It is possible for an epoch to have 0 voting campaigns, which means noone will have voting points, noone can claim the reward. In this case, all of the reward can be used to buy KNC and burn.

## Rebate
Rebate is part of the fee that the FeeHandler of each market collects to pay back reserves to compensate their dedication to run market making and bring liquidity to the whole nework. Rebate is accumulated for each reserve until they claim it, they can claim it whenever they want.

Not all reserve types are allowed to take rebate. The rebate entitlement is decided by the DAO via a General Campaign and will be set manually by the Network admin.

The amount of rebate equals to `network_fee_for_the_handled_volume * rebate_percentage`. The `rebate_percentage` is decided by the DAO via BRR campaigns.

It is not possible for the Dao Operator to give rebate entitlement flag to a feeless reserve.

### Rebate-less reserve
Every reserve comes with one reserve type, each reserve type has a **rebate entitlement flag** to determine if it is going to receive a rebate. If a reserve type has its **rebate entitlement flag** set to False, all reserves of that type are called **rebate-less reserve** and they will get no rebate.

It is possible for a normal reserve (not feeless) to be **rebate-less**, in this case, there will be some left over fee which is not for rebate. That left over fee amount will be allocated for extra rewards.

## Burn
Burn is the last part of the network fee collected by each market's FeeHandler. The burn amount will be accumulated on each FeeHandler, ready to use to buy KNC to burn.

The amount of burn is calculated based on `network_fee * burn_percentage` formula. The `burn_percentage` is decided by the DAO via BRR campaign.

If in one epoch, noone can claim the reward (either there is no voting campaigns or noone has KNC staked to earn voting points), the fee supposed to be the reward will be converted to burn.

Anyone can call `burnKNC` function from each FeeHandler, the transaction is called **burn transaction**. Each transaction will use `min(eth amount available to burn, max_eth_to_burn_per_tx)` of the **Burn** to buy KNC and burn them.

## Voting Campaign
A voting campaign is a set of options and parameters for voters to vote. The purpose of a voting campaign is to draw a consensus of the DAO over the options. Most of the time, the consensus is to choose the best option among the provided ones.
Voting campaign parameters determine when it starts, how long it lasts and how it will be concluded. A voting campaign always has the following parameters:
- `start_timestamp`: the timestamp in seconds when it starts
- `end_timestamp`: the timestamp when it ends. If a vote happens in a timestamp greater than this `end_timestamp`, the vote is invalid. A voting campaign can only start in the current epoch or the next one, and end in the same epoch.
- `min_knc_voted_percentage`: the minimal staked KNC required to vote for the campaign in order to conclude the campaign. If there are too little staked KNC voted for the campaign, the campaign is considered unsuccessful. There is no winning option in this case.
- `c`, `t`: the coefficients in `c - t * (total_vote/supply)` to determine the threshold of a winning option (the option that is voted the most) to be the campaign's conclusion. If the winning option's vote percentage over `total_vote` is smaller than the threshold, the campaign is considered as a tie and there is no winning option in this case. 

There are 3 specific types of voting campaign: Fee Campaign, BRR Campaign and General Campaign. Depends on the type of the voting campaign, the meaning of the options change accordingly. They will be will be defined in the following sections.

### Fee Campaign
Fee campaign is one type of voting campaigns. It is used to determine the network fee percentage for the whole network. Fee campaigns also need all of the parameters of a voting campaign.
The options for a fee campaign are always integers in the range of [0, 5000) which means the percentage in bps of the trade will be taken as the network fee.

When a fee campaign is concluded successfully, its winning option will be used as the fee percentage for the network as soon as the next epoch starts. 

### BRR Campaign
BRR campaign is one type of voting campaigns. It is used to determine the Burn/Reward/Rebate percentage in bps for the next epoch. BRR campaigns also need all of the parameters of a voting campaign.
The options for a BRR campaign represent options for the BRR distribution. Each option represents 2 percentage value (in bps) for Rebate and Reward. The Burn is automatically calculated as `10000 - rebate - reward`. Most of the time, BRR campaign will have 4 options as in the following example (assuming the current BRR of the network is 5%-65%-30%):
1. 3000-6500 (no change, keeping the old distribution, 5% burn, 65% reward, 30% rebate)
2. 2570-7000 (pro reward, lower rebate and burn proportionally, 4.3% burn, 70% reward, 25.7% rebate)
3. 2840-6160 (pro burn, lower reward and rebate proportionally, 10% burn, 61.6% reward, 28.4% rebate)
4. 3500-6040 (pro rebate, lower reward and burn proportionally, 4.6% burn, 60.4% reward, 35% rebate) 

When a BRR campaign is concluded successfully, its winning option will be used as the BRR configuration for the network as soon as the next epoch starts. 

### General campaign
General campaign is one type of voting campaigns. It is used by the DAO to make decision in general. The campaign will be in the form of giving a set of option IDs and a link to the off-chain discussion.

When a general campaign is concluded successfully, its winning option will be used as the configuration for the Network admin or DaoOperator to manually set on the smart contract system. On the other hand, the winning option can be any decisions as the guideline for Kyber team and the whole community to follow.

## DaoOperator
DaoOperator is an ethereum wallet (a multisig) to manually set the following configuration for the Dao:
- Create a voting campaign
- Cancel a voting campaign before it starts
- Set the amount of quote token that is used to buy KNC and burn for 1 transaction
- Set the sanity price contract to protect KNC price during burning process
- Set network address for FeeHandler
- Set DEX address for FeeHandler to buy KNC to burn

## Voter
An ethereum address that votes on Kyber DAO contract is called a voter.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
