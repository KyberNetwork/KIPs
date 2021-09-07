---
kip: 14
title: Allocate additional 5M KNC from the ecosystem fund
status: Active
type: Mint KNC
authors: Kyber Network team
created: 2021-09-06
---

```
campaign_type: binary
executor: short timelock executor
voting_power: current staked voting power
execution: transfer 5M KNC from ecosystem funds to daoOperator
start_timestamp: 1630998000 (Tue, 7 Sep 2021 07:00:00 UTC)
end_timestamp: 1631603220 (Tue, 14 Sep 2021 07:07:00 UTC)
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 40000000000000000

```

## Summary

There are approximately `24,912,378 KNC` tokens remaining in the Kyber ecosystem fund after allocating for liquidity mining campaigns on Ethereum, Polygon and BSC.

KyberDMM will officially launch on Avalanche soon. There are also many projects on these various chains that are proposing to be part of the ‘Rainmaker’ liquidity mining program. KIP-14 enables the DAO operator to allocate 5M KNC (from the remaining KNC in the ecosystem fund) to be utilised in the upcoming ‘Rainmaker’ joint liquidity mining campaigns based on this [framework](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-8.md)

Out of the 5M KNC, 1.4M KNC (~$3M) will be first allocated to 6 eligible pools for the Rainmaker liquidity mining program on Avalanche. This was already approved in [KIP-13](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-13.md)

In addition to the initial 6 incentivised pools on Avalanche, we’d also like to allocate 387,600 KNC(~$833k) tokens to a USDT-USDC pool. Community members have recently highlighted that USDC is a popular stablecoin that is lacking liquidity on Avalanche as it was just supported, so this presents an excellent opportunity for KyberDMM to enhance USDC liquidity and capture more USDC volume on Avalanche.

Ideally, Rainmaker on Avalanche would start with the following 7 pools, each allocated with approximately $833,333 worth of KNC incentives for liquidity providers:

- USDT-USDC (AMP=400)
- USDT-DAI (AMP=400)
- AVAX-ETH (AMP=1.5)
- AVAX-DAI (AMP=1.5)
- WBTC-ETH (AMP=2)
- KNC-AVAX (AMP=1.5)
- KNC-ETH (AMP=1.9)

After allocating for the above Avalanche-based pools, the remaining KNC will be utilised for upcoming campaigns in the near term, based on individual project proposals.