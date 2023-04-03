---
kip: 22
title: Revising % Fee Ratio between KyberDAO and LPs
status: Active
type: Updating DAO Configuration
authors: Kyber Network team
created: 2023-04-03
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: Calibrate % fee ratio that goes to KyberDAO and LPs
start_timestamp: 1680591600 (Tuesday, April 4, 2023 2:00:00 PM GMT+7)
end_timestamp: 1681196820 (Tuesday, April 11, 2023 2:07:00 PM GMT+7)
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 40000000000000000 (4%)

```

## Summary

Trading fees is an important element influencing liquidity providers (LPs) and liquidity growth on KyberSwap, while incentivizing governance participation on KyberDAO. Currently, [10% of the KyberSwap fees](https://docs.kyberswap.com/kyber-dao/fees-to-kyber-dao) collected from trades through liquidity pools are sent to KyberDAO to be used as voting rewards and the other 90% going to LPs.

This KIP proposes that 6% of the current fees allocated to liquidity providers (LPs) be repurposed to KyberDAO instead; with the new overall fee ratio being **16% to KyberDAO and 84% to LPs**. This change will begin only on Ethereum first, with a plan to roll it out to other chains at a later date.

Of the 16% of fees going to KyberDAO, 10% will remain as voting incentives, while the extra 6% will be allocated transparently for various operations with the purpose of increasing user growth. This would start with partial gas refunds for eligible KyberSwap traders, but would eventually include product, marketing, and business development operations. 

The aim is to attract more users that would in turn result in higher trading volume and more earnings for LPs and KNC voters. 

Community discussion around this KIP can be found in the [governance forum](https://gov.kyber.org/t/discussion-kip-22-revising-fee-ratio-between-kyberdao-and-lps/1305). For this KIP to be approved, a minimum quorum of 4% of Total KNC supply is required for the winning option, with a vote differential of 0.01%.

## Motivation

KyberSwap has been giving 90% of pool fees collected from trades to liquidity providers. This is higher than DEXes such as Curve (50%) and Sushi (83.33%). We have since captured substantial volume share in the market despite having a fraction of the Total Value Locked (TVL) of our competitors. 

- [Top 3 DEX on Optimism](https://defillama.com/dexs/chains/optimism)
- [Top 5 DEX on Polygon](https://defillama.com/dexs/chains/polygon)
- [Top 6 DEX on Arbitrum](https://defillama.com/dexs/chains/arbitrum)
- [Top 8 DEX on Ethereum](https://defillama.com/dexs/chains/ethereum)

We have also attracted many smart liquidity providers who have earned over $13M in LP fees as a result. These milestones are a reflection of our highly capital-efficient liquidity pools which help LPs earn more and maximize their use of capital.

However, we have ambitious plans to gain even more traders and LPs on KyberSwap and we need to take immediate action to find an additional source of funding for our upcoming activities, without being solely reliant on the KNC in our limited KyberDAO ecosystem fund.

Given that KyberSwap has reached a strong starting foundation of traders, liquidity providers, TVL, and partners, KyberDAO is well positioned to be allocated more fees without inhibiting KyberSwap’s current momentum.

Extra fees allocated to KyberDAO will go towards driving even higher user growth on KyberSwap through gas refunds, as well as various marketing and business development operations. This would in turn help increase the number of LPs and TVL (leading to better overall rates), as well as traders (leading to higher overall volume and fees).

## Fee Allocation Details

We propose to increase the KyberDAO fee portion of trading fees to 16% for all pools and fee tiers, while reducing the portion going to LPs to 84%. This fee change will be deployed first on Ethereum as a pilot program. Depending on the results of a performance review, the team might consider deploying to more chains supported on KyberSwap.

Of the fees going to KyberDAO, 10% will go to voters, while 6% will be allocated by KyberDAO immediately for KyberSwap operations, starting with partial gas refunds for eligible traders.

- 84% of the fees are given to LPs
- 10% gets converted to KNC rewards, and distributed to voters
- 6% gets allocated to upcoming KyberSwap operations, starting with partial gas refunds

At a later stage, once we have reached a suitable level of user growth, the fee allocation to KyberDAO may be readjusted; to increase fees for KNC voters or mitigate the short-term decrease in fees for LPs. 

Furthermore, if a new mint of KNC funds is approved by KyberDAO in the future, a portion could be strategically allocated to voters or LPs. Distribution could even be retroactive; benefiting past voters that supported KyberSwap in achieving our user and liquidity growth targets.

## Considerations

When proposing this KIP, we sought to ensure that the reduction of fees for LPs would not severely impact their APR% and by extension the attractiveness of our KyberSwap liquidity pools. As such, we conducted a review of the DEX space to consider the competitiveness level of our LP fee %. Our findings indicate that an LP fee share of 84% as proposed remains within the minimum competitive threshold when compared to other DEXes.

We expect most existing LPs to continue adding liquidity on KyberSwap pools to enjoy the high capital efficiency and other benefits, while new LPs and partners would start using KyberSwap after learning about these benefits and feature improvements from upcoming growth activities.

## Conclusion

Increasing the fee % allocated to KyberDAO and allocating the extra fees to KyberSwap at this stage would provide the team with additional firepower to achieve our desired user, volume, and TVL growth in a more sustainable manner, without depending solely on KNC incentives from the ecosystem fund. LPs may experience a marginal, short-term decrease in fees from their pools, but they (along with KNC voters) would potentially enjoy higher overall volume and fees once our growth activities are in full swing this year.