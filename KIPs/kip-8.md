---
kip: 8
title: Adding Kyber DMM to KyberDAO and Establishing an Ecosystem Growth Fund
status: Active
type: Mint KNC
authors: Kyber Network team
created: 2021-05-16
---

```
executor: long timelock executor
voting_power: current staked voting power
execution:
  1. mint 12615176.4 KNC to the Dao Operator
  2. mint 29435411.6 KNC to the short timelock executor
start_timestamp: 621321627 (Tuesday, May 18, 2021 07:07:07 GMT+00:00)
end_timestamp: 1621926426 (Tuesday, May 25, 2021 07:07:06 GMT+00:00)
```

## Summary

Based on in-depth community discussion over a few weeks, the Kyber team is proposing that the Kyber DMM (Dynamic Market Maker) protocol gets added as a new liquidity protocol on Kyber’s liquidity hub, with a portion of fees going to the KyberDAO.

The team is also proposing that 42M KNC be minted and managed by KyberDAO as part of a 12-month Kyber Ecosystem Growth Fund for the purpose of increasing Kyber’s liquidity and adoption through various activities including liquidity mining and ecosystem collaborations.

30% of the fund (12.6M KNC) will be first allocated to a genesis liquidity mining activity to incentivize liquidity providers on the DMM for 3 months, with the utilisation of the remaining 70% being determined by KyberDAO at a later date. 

Any remaining KNC in the fund that isn’t used by the end of the 12-month period (starting from the first mint) will be burnt.


## Motivation

Currently, DMM is a standalone protocol that is not part of Kyber’s liquidity hub. We are proposing to add DMM to the liquidity hub, thereby allowing KyberDAO to accrue trading fees from the protocol.

There is also broad consensus in the community for the need for a Kyber Ecosystem Growth Fund and utilising a portion of it for liquidity mining to bootstrap liquidity and reward early adopters of the Kyber DMM.  



*   **Bootstrap liquidity:** Additional liquidity incentives are necessary to attract more liquidity providers to the DMM as soon as possible. Ideally, with the added bonus of liquidity incentives, the DMM can be the most capital efficient and attractive venue in DeFi to add liquidity for the selected token pairs.
*   **Showcase Kyber DMM’s benefits to liquidity providers:** If they are incentivized to use the amplified pools, liquidity providers will naturally learn about and enjoy the benefits of high capital efficiency and dynamic fees.
*   **Bring more DeFi participants and value into the Kyber ecosystem:** More liquidity providers using amplified pools would mean more of them receiving KNC rewards and becoming part of the Kyber ecosystem and community, with the ability to stake KNC and vote on the KyberDAO. By receiving KNC, liquidity providers not only gain a useful asset, but also a stake in DeFi’s liquidity infrastructure.


## Adding Kyber DMM to KyberDAO

The DMM protocol will be added to Kyber’s liquidity hub and owned and governed by KyberDAO. 

KyberDAO will allocate 12.6M KNC for a liquidity mining program to help bootstrap liquidity and adoption for the DMM. In return for these KNC incentives and the strong support provided by the Kyber community, 10% of the DMM liquidity provider fees collected from trading activities will be sent to KyberDAO (the other 90% goes to liquidity providers).

In addition, we propose that KyberDAO converts those fees to KNC tokens to reward KNC holders who stake and vote. This allows for a positive loop where KNC holders have the ability to easily stake KNC rewards for additional voting power and rewards.


## Proposed Implementation of Kyber Ecosystem Growth Fund

Mint KNC Allocation for Liquidity Incentives

Current KNC Total Supply (17th April): **210,252,943**

Ecosystem Fund KNC Pool to mint: **42,050,588 (20% of current supply)**

30% of the additional KNC will be used for the first liquidity mining program which will last for 3 months. Utilization of the remaining 70% to be determined at a later stage.

### Eligible Liquidity Pools

Amplified pools (AMP>1) on Kyber DMM provide much higher capital efficiency compared to typical liquidity platforms. We are proposing 5 amplified pools that we feel are the best suited for the initial liquidity incentive program, based on the current trading behaviour and trends in the DeFi space. 

The more liquidity you provide on the specific pool, and for a longer period, the greater the share of the total reward pool (12.6M KNC) you receive.

Each of these selected pools will receive an equal amount of 2.52M KNC rewards.

The 5 suggested pools and their AMP factors:

| Pair      | AMP* | Reason for incentivizing the pool                                                                                                                                                                                                                                           |
|-----------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| USDT-USDC | 200  | Stablecoins pegged to the US Dollar such as USDT and USDC, are among the most traded and held tokens on Ethereum. Strongly correlated/stable pairs also provide the best showcase of the high capital efficiency possible on Kyber DMM.                                     |
| USDT-ETH  | 1.5  | Stablecoins pegged to the US Dollar such as USDT and USDC, are among the most traded and held tokens on Ethereum. Paired together with ETH, this would be a popular pool to hold USDT while maintaining exposure to ETH.                                                    |
| USDT-WBTC | 1.5  | Wrapped Bitcoin (WBTC) is the most widely-used ERC-20 version of Bitcoin and a popular choice for liquidity providers.                                                                                                                                                      |
| WBTC-ETH  | 2    | Wrapped Bitcoin (WBTC) is the most widely-used ERC-20 version of Bitcoin and a popular choice for liquidity providers. Paired together with ETH, this would be a popular pool to maintain exposure to both BTC and ETH.                                                     |
| KNC-ETH   | 1.9  | To enhance KNC liquidity and encourage KNC holders to lock up their tokens for a prolonged period to govern Kyber Network, we propose that liquidity incentives be awarded to an amplified KNC-ETH pool. This also acts as a natural counter against inflationary pressure. |

**AMP = Amplification factor. Amplified pools have higher capital efficiency. Higher AMP, higher capital efficiency within a tighter price range.*

### KNC Rewards Emission

Upon successfully adding liquidity by depositing the required tokens into the eligible campaign pools, users receive DMM-LP pool tokens representing their pool share. DMM-LP tokens have to be staked in designated smart contracts to receive KNC liquidity incentives. 

KNC liquidity incentives are awarded to every liquidity provider that adds liquidity to eligible pools, with the reward amount based on their share of the pool.

By default, KNC liquidity mining reward distribution will be based on a linear distribution. The same reward is released every block. The longer you provide liquidity on the DMM, the more KNC rewards received during the 3 months period.


### Claiming KNC Rewards: Linear Vesting

Users are required to stake their DMM-LP tokens to a farming contract that will calculate and allocate rewards over time (a vesting period). The implementation of this farming contract is modified from the [FairLaunch contract](https://bscscan.com/address/0xa625ab01b08ce023b2a342dbb12a16f2c8489a8f#code) of [Alpaca Finance](https://www.alpacafinance.org/).

When users take action to harvest their rewards, they don’t receive the rewards immediately. Instead, rewards are sent to a RewardLocker contract, which allows users to vest their rewards linearly over blocks. We denote the vesting period to be **X** blocks. 

For the first liquidity incentive program, we are proposing a vesting period of **30 days**. At 12-15 secs per block, this is estimated to be **200,000 blocks**.

Each reward harvested vests linearly by block, starting from the block that a user performs the harvest. The user can claim unlocked rewards from the RewardLocker at any time once that particular harvested reward has fully vested. 

This linear vesting mechanism is an essential governance safeguard, further ensuring KyberDAO governance stability and a smoother KNC reward distribution process. Claimed KNC rewards can be freely utilised, for example to add liquidity into the KNC/ETH pool or to stake in KyberDAO to vote and earn more KNC rewards.

**Example: 30-day Vesting period (~ 200,000 blocks)**

For this example, we take lockDuration as X = 200,000 blocks:
|     Block    |                    Action                    |                                                                                                                                                                        Description / Explanation                                                                                                                                                                       |
|:------------:|:--------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| t0 = 0       | User harvests reward, get 100,000 KNC        | 100,000 KNC linearly vests over X = 200,000 blocks, where 100,000/200,000 KNC is unlocked per block. Full amount of 100,000 KNC is unlocked at t0 + X = block 200,000.                                                                                                                                                                                                 |
| t1 = 100,000 | User harvests reward, get 150,000 KNC        | 150,000 KNC linearly vests over X = 200,000 blocks, where the full amount is unlocked after t1 + X = block 300,000. The following can be claimed from RewardLocker: For t0: 100,000 * (t1 - t0) / 200,000 KNC                                                                                                                                                          |
| t2 = 120,000 | User harvests reward, gets 500,000 KNC       | 500,000 KNC linearly vests over X = 200,000 blocks, where the full amount is unlocked after t2 + X = block 320,000. The following can be claimed from RewardLocker: For t0: 100,000 * (t2 - t0) / 200,000 KNC For t1: 150,000 * (t2 - t1) / 200,000 KNC                                                                                                                |
| t3 = 150,000 | User makes a claim of t0 vesting schedule    | For t0: user receives 100,000 * (t3 - t0) / 200,000 = 75,000 KNC of the vested rewards.                                                                                                                                                                                                                                                                                |
| t4 = 220,000 | User makes a claim for all vesting schedules | For t0: reward has fully vested at block 200,000, user receives full reward (minus the reward that use has claimed at t3), so user gets the remaining (100,000 - 75,000) = 25,000 KNC For t1: user receives 150,000 * (t4 - t1) / 200,000 = 90,000 KNC of the vested rewards. For t2: user receives 500,000 * (t4 - t2) / 200,000 = 250,000 KNC of the vested rewards. |
Each pool can have its reward duration extended, so that users need not migrate from one `poolId` to another.

The updating of the pool and user rewards amounts are contained in the [updatePoolRewards](https://docs.google.com/document/d/1HS6JwDdUNW0-QAhfPFjVgdgyPijqsvkkMjWK0XFgP34/edit#heading=h.3l6qw0uj2sij) and [updateUserRewards (Internal Function)](https://docs.google.com/document/d/1HS6JwDdUNW0-QAhfPFjVgdgyPijqsvkkMjWK0XFgP34/edit#heading=h.j0048idbe3w4) functions respectively. The logic is similar to Synthetix’s [StakingRewards](https://github.com/Synthetixio/synthetix/blob/master/contracts/StakingRewards.sol) contract.

Multiple vesting functions are added to the RewardLocker contract to allow users optimizing gas consumption when vesting their rewards.


## Conclusion

We strongly believe that the addition of Kyber DMM into Kyber Network, the creation of the 12-month Kyber Ecosystem Growth Fund, as well as the subsequent liquidity incentive program will greatly boost liquidity and adoption of the Kyber DMM protocol. These initiatives will also result in a lot more KNC holders and help grow the Kyber ecosystem.

As always, all important decisions pertaining to new token generation/burning, new protocols, and growth initiatives, will be decided as one Kyber community in a transparent manner. As a community, a key objective for us is to ensure an increase in liquidity on Kyber DMM and that KNC continues to play a valuable and central role in the Kyber and DeFi ecosystem.
