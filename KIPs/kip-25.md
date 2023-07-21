---
kip: 25
title: Revising % Fee Ratio between KyberDAO and LPs on all chains
status: Active
type: Updating DAO Configuration
authors: Kyber Network team
created: 2023-07-21
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: Calibrate % fee ratio that goes to KyberDAO and LPs
start_timestamp: 1690268820 (Tuesday, July 25, 2023 2:07:00 PM GMT+7)
end_timestamp: 1691478420 (Tuesday, August 8, 2023 2:07:00 PM GMT+7)
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 40000000000000000 (4%)

```
## Summary

Previously, following the approval of [KIP-22](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-22.md), KyberSwap updated the % fee ratio between KyberDAO and LPs (liquidity providers) on Ethereum to 16% and 84% respectively. However, on other chains where KyberSwap is deployed, the old fee ratio of 10% to KyberDAO and 90% to LPs is still being used. 

In this KIP, we propose to update all other chains to match the fee ratio deployed on Ethereum (**16% to KyberDAO and 84% to LPs**).

Of the 16% of fees going to KyberDAO, 10% will remain as voting incentives, while the extra 6% will be allocated transparently for various KyberSwap operations with the purpose of increasing user growth. This would start with partial gas refunds for eligible KyberSwap traders, but would eventually include product, marketing, and business development operations. 

The aim is to attract more users that would in turn result in higher trading volume and more earnings for LPs and KNC voters. 

Community discussion around this KIP can be found in the [governance forum](https://gov.kyber.org/t/kip-25-revising-fee-ratio-between-kyberdao-and-lps-on-all-chains-upcoming/1928). For this KIP to be approved, a minimum quorum of 4% of Total KNC supply is required for the winning option, with a vote differential of 0.01%.

## Motivation

Trading fees is an important element influencing liquidity providers (LPs) and liquidity growth on KyberSwap, while incentivizing governance participation on KyberDAO.

Currently, apart from Ethereum, KyberSwap has been giving 90% of pool fees collected from trades to LPs. This is higher than DEXes such as Curve (50%) and Sushi (83.33%). 

We have since captured substantial volume share in the market despite having a fraction of the Total Value Locked (TVL) of our competitors. 

- [Top 4 DEX on Optimism](https://defillama.com/dexs/chains/optimism)
- [Top 4 DEX on Arbitrum](https://defillama.com/dexs/chains/arbitrum)
- [Top 5 DEX on Polygon](https://defillama.com/dexs/chains/polygon)
- [Top 8 DEX on Avalanche](https://defillama.com/dexs/chains/avalanche)

We have also attracted many smart liquidity providers who have earned over $13M in LP fees as a result. These milestones are a reflection of our highly capital-efficient liquidity pools which help LPs earn more and maximize their use of capital.

However, we have ambitious plans to gain even more traders and LPs on KyberSwap and we need to take immediate action to find an additional source of funding for our upcoming activities, without being solely reliant on the KNC in our limited KyberDAO ecosystem fund.

Given that KyberSwap has reached a strong starting foundation of traders, liquidity providers, TVL, and partners, KyberDAO is well positioned to be allocated more fees without inhibiting KyberSwap’s current momentum.

Extra fees allocated to KyberDAO will go towards driving even higher user growth on KyberSwap through gas refunds, as well as various marketing and business development operations. This would in turn help increase the number of LPs and TVL (leading to better overall rates), as well as traders (leading to higher overall volume and fees).

## Fee Allocation Details

We propose to increase the portion of trading fees going to KyberDAO to 16% for all pools and fee tiers, while reducing the portion going to LPs to 84%. This would apply to all chains supported by KyberSwap.

Of the fees going to KyberDAO, 10% will go to voters, while 6% will be allocated by KyberDAO immediately for KyberSwap operations, starting with partial gas refunds for eligible traders.

**In summary:**

- 84% of fees to LPs
- 10% converted to KNC rewards, and distributed to voters
- 6% allocated to upcoming KyberSwap operations, starting with partial gas refunds

At a later stage, once we have reached a suitable level of user growth, the fee allocation to KyberDAO may be readjusted; to increase fees for KNC voters or mitigate the short-term decrease in fees for LPs.

## Considerations

When proposing this KIP, we sought to ensure that the reduction of fees for LPs would not severely impact their APR% and by extension the attractiveness of our KyberSwap liquidity pools. As such, we conducted a review of the DEX space to consider the competitiveness level of our LP fee %. Our findings indicate that an LP fee share of 84% as proposed remains within the minimum competitive threshold when compared to other DEXes. 

In addition, during our ~3-month trial phase on Ethereum, we found no major behavioral changes or negative sentiments from LPs due to the change in the % fee ratio.

We expect most existing LPs to continue adding liquidity on KyberSwap pools to enjoy the high capital efficiency and other benefits, while new LPs and partners would start using KyberSwap after learning about all its advantages from upcoming growth and educational activities.

Furthermore, a portion of newly minted KNC funds approved by KyberDAO in the future could be strategically allocated to voters or LPs. Distribution could even be retroactive; benefiting past voters that supported KyberSwap in achieving our user and liquidity growth targets.

## Conclusion

Increasing the fee % allocated to KyberDAO and allocating the extra fees to KyberSwap operations would provide the team with additional firepower to achieve our desired user, volume, and TVL growth in a more sustainable manner, without depending solely on KNC incentives from the ecosystem fund. LPs may experience a marginal, short-term decrease in fees from their pools, but they (along with KNC voters) would potentially enjoy higher overall volume and fees once our growth activities pick up momentum. The latest % fee ratio details would be reflected on our documentation [here](https://docs.kyberswap.com/governance/kyberdao/fees-to-kyberdao).