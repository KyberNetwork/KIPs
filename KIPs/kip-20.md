---
kip: 20
title: KNC Ecosystem Fund Allocation
status: Active
type: KNC Ecosystem Fund Allocation
authors: Kyber Network team
created: 2022-05-05
---

```
campaign_type: binary
executor: short timelock executor
voting_power: current staked voting power
execution: KNC Ecosystem Fund Allocation
start_timestamp: 
end_timestamp: 
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 

```
## Summary

42M KNC (Kyber Network Crystal) tokens were minted after KIP-8 in 2021 and managed by KyberDAO as a Kyber Ecosystem Growth Fund for the purpose of increasing Kyber’s liquidity and adoption through various activities through 2022, including liquidity mining and ecosystem collaborations.

There are approximately 23,747,562 KNC remaining (~$71.2M at $3 per KNC) in the fund after key liquidity mining campaigns on Ethereum, Polygon, BNB Chain, Avalanche, and BitTorrent, as well as those with partners such as xToken, xDollar, Jarvis Network, DeFi Warrior, Creator, Elpis Battle, GemUni, StepHero, APEIN, DYP Protocol, Pegaxy, Sipher, Unbound Finance, Evrynet, and Benqi.

Now that our KyberSwap DEX aggregator has been deployed on 11 chains (many more in the pipeline), further boosted by an upcoming launch of Elastic-type liquidity pools that offers even greater capital efficiency for liquidity providers, we propose that KyberDAO utilize the remaining KNC for even more growth activities on KyberSwap, instead of simply burning the KNC. This KIP was also based on community discussion in our [forum](https://gov.kyber.org/t/discussion-knc-ecosystem-fund-allocation/1047).

Proposed Use Cases for Remaining KNC Funds

- Trading and Liquidity Growth | ~62%
- Milestone-based Ecosystem Grants | ~20%
- 5-year Anniversary Marketing Activities | ~16%
- Bonus rewards for KyberDAO staking and voting | ~2%

### Motivation
Our past trading and liquidity bootstrapping activities on KyberSwap have led to some degree of success. Since the launch of the new KyberSwap version last year, thousands of liquidity providers have earned approximately $8M in trading fees and KNC voters $1M in rewards. Total value locked (TVL) in our pools reached $140M recently and the value of KNC staked on KyberDAO is worth over $120M. In addition, we now have almost [10,000 KNC holders](https://etherscan.io/token/0xdeFA4e8a7bcBA345F687a2f1456F5Edd9CE97202#balances) that are part of the Kyber community and ecosystem, as well as close ties with many top DeFi and GameFi projects.

In order to continue this positive growth, we would like to further allocate and utilize the KNC in our ecosystem growth fund. Most popular DEXes carry out some form of liquidity mining or incentive program to attract users, so it is necessary for KyberSwap to do the same to stay competitive.

KyberSwap already has several technical advantages over other DEXes in terms of best rates through DEX aggregation and capital-efficient liquidity pools, and KNC incentives would further amplify our DeFi mindshare and user acquisition on all supported chains.

### Proposed Allocation for Remaining KNC in the Fund

Below we present an overview of the KNC allocation for the different initiatives; namely trade & liquidity mining (further split into incentives per chain), milestone-based grants, marketing activities, and bonus KyberDAO voter rewards. Note that this KNC in our ecosystem growth fund is managed by KyberDAO and is separate from the Kyber team’s treasury.

Total KNC remaining in the fund: 23,747,562 KNC

**1. For Trading and Liquidity Growth**

KNC Amount: 14,697,562 KNC (~62%)

We plan to continue working with the foundation/core team of each chain to devise strategic trading and liquidity mining initiatives that would bring tens of thousands more users to KyberSwap. To complement this, we have been optimizing our pools and liquidity mining strategy to attract more sustainable, long-term liquidity provision instead of just ‘hot money’ mercenary capital.

We propose that the bulk of the remaining KNC be used for activities related to trading and liquidity growth. Some of this KNC would also be used for seeding initial pools, bridging KNC into different chains (supporting KNC on cross-chain bridges), and other ad hoc activities.

The proposed allocation below is based on a few factors including on-chain volume, liquidity, and Dapp activity, and the amount of incentives already allocated before this phase. Allocation % might change given the dynamic nature of each chain, subject to community feedback and future KyberDAO votes.

|Chain|% Allocation from Trading & Liquidity Growth funds|
| --- | --- |
|Ethereum|5%|
|Polygon|9%|
|BNB|9%|
|Avalanche|2%|
|Fantom|10%|
|Arbitrum|8%|
|Aurora|8.5%|
|Cronos|6%|
|Oasis|4%|
|BitTorrent Chain|1%|
|Velas|0.5%|
|Future liquidity mining on other chains and ad hoc activities|37%|

Within each chain that is currently supported on KyberSwap, we have identified certain token pairs as high priority due to their trading volume and popularity. Stablecoin and correlated pairs are especially critical, since KyberSwap’s high capital efficiency is best observed on such pairs. We plan to seed and use KNC to incentivize these liquidity pools, among others.

|Chain|Pairs|
| --- | --- |
|Ethereum|USDC-USDT, USDC-KNC, USDC-ETH, FRAX-USDC, USDC-WUST, WBTC-ETH, USDT-ETH, DAI-USDC, DAI-ETH|
|Polygon|USDC-USDT, DAI-USDC, DAI-USDT, KNC-USDC, USDC-miMATIC, USDC-UST, WBTC-MATIC, USDT-ETH, USDT-MATIC, USDC-MATIC, USDC-ETH, WBTC-USDC, MATIC-ETH, KNC-ETH, KNC-MATIC, ETH-DAI|
|BNB Chain|USDC-USDT, USDT-BNB, BUSD-USDC, DAI-USDC, DAI-USDT, DAI-BUSD, KNC-USDT, KNC-USDC, KNC-ETH, KNC-BNB, BUSD-WUST, BUSD-USDT, BUSD-BNB, ETH-BNB, ETH-BUSD|
|Avalanche|USDC-USDT, DAI.e-USDC, DAI.e-USDT, AVAX-DAI.e, AVAX-USDC, AVAX-USDC.e, AVAX-USDT, AVAX-USDT.e, AVAX-WBTC, AVAX-WETH.e, USDT-USDT.e, USDC-USDC.e, AVAX-MIM, USDC-MIM, miMATIC-USDC, UST-USDC, UST-AVAX, KNC-USDC, KNC-WETH.e, KNC-AVAX|
|Fantom|USDC-USDT, DAI-USDC, DAI-USDT, KNC-USDC, KNC-ETH, KNC-FTM, ETH-FTM, ETH-WBTC, USDC-miMATIC, FTM-WBTC, FTM-MIM, FTM-fUSDT, FTM-UST, USDC-TUSD, USDC-UST, USDC-FTM, USDC-ETH|
|Arbitrum|USDC-USDT, DAI-USDC, DAI-USDT, FRAX-USDC, USDs-USDC, KNC-USDC, KNC-ETH, WBTC-ETH, ETH-USDT, ETH-USDC, DAI-ETH, rETH-ETH|
|Aurora/NEAR|USDC-DAI, USDC-USDT, USDT-DAI, USDC-RUSD, USDC-atUST, AURORA-ETH, AURORA-USDC, AURORA-wNEAR, AURORA-KNC, wNEAR-KNC, USDC-KNC, wNEAR-ETH, wNEAR-USDC, wNEAR-USDT, wNEAR-WBTC, USDC-ETH, ETH-KNC|
|Cronos|USDC-DAI, USDT-DAI, USDC-USDT, TUSD-USDC, DUSD-USDC, KNC-CRO, KNC-USDC, KNC-ETH, ETH-USDC, CRO-WBTC, CRO-ETH, CRO-USDT, CRO-USDC|
|Oasis Emerald|USDC-USDT, USDC-DAI, USDT-DAI, UST-USDT, ROSE-USDC, ROSE-USDT, ROSE-ETH, USDT-BTC, ROSE-KNC, USDC-KNC, ETH-KNC, USDT-ETH, USDC-ETH|
|BitTorrent Chain|Key pools already seeded and live|
|Velas|USDC-USDT, DAI-USDC, DAI-USDT, USDV-BUSD, USDV-DAI, KNC-USDC, KNC-ETH, ETH-USDC|

**2. For Milestone-based Ecosystem Grants**

KNC Amount: 4,700,000 KNC (~20%)

Besides the pre-allocated trading and liquidity mining campaigns for the token pairs mentioned above, we plan to offer 4,700,000 KNC (~$14M at $3 per KNC) in ecosystem grants to top DeFi or GameFi projects that fulfill certain criteria and milestones on KyberSwap. This would incentivize a wide variety of token liquidity on KyberSwap.

We would develop a fair and transparent process that allows any project on supported chains to compete to hit certain liquidity and volume milestones and tiers in order to obtain an appropriate share of the total KNC rewards.

The exact process and minimum qualifying criteria would be determined later, but would include:

* Creation of a liquidity pool
* Achieving a minimum amount of liquidity (TVL)
* Achieving a minimum 24H trading volume

**3. For 5-Year Anniversary Marketing Activities**

KNC Value: $12M (~16%)

September 2022 will mark the 5-Year Anniversary of Kyber Network. This is a momentous occasion that provides the opportunity for Kyber to reward our loyal supporters, look back at our progress over the years, and highlight how KyberSwap is the best decentralized multi-chain platform for traders and liquidity providers alike. Our core marketing objective is to get as many users as possible to be aware of our benefits and try using KyberSwap.com

Based on our estimations, we propose an allocation of ~$12M worth of KNC for various marketing activities, including:

* Paid advertisements
* Crypto event sponsorships
* Community rewards e.g. for AMAs, top supporters, ambassadors
* Trading contests and other user adoption campaigns
* Educational content with partners

**4. For Bonus KyberDAO Voting Rewards**

KNC Value: $1.5M (~2%)

Staking KNC in advance enables anyone to vote and earn KNC rewards derived from a portion of trading fees on KyberSwap. As we work on redesigning [KyberDAO](http://kyber.org) to implement gasless voting and migrating the UI to KyberSwap.com, as well as improving KNC utility, we plan to reward KyberDAO voters for their strong support and contribution to KyberSwap’s development.

~$1.5M worth of KNC would be proposed as allocation for activities related to KyberDAO staking and voting, some of which could be retroactive and some as future drops.

## Important Considerations

**Structured Flexibility:** It is important to note that although we have proposed a high-level allocation and structure for the KNC funds to be used in the coming months, KyberSwap has to adapt to changing DeFi trends. As such, specific percentages, KNC value, and details for each category may change, subject to a new KIP and approval from the KyberDAO via a vote. For example, certain chains or token pairs may become substantially more popular at a later stage, and thus require more resources devoted to them.

**Improving KNC Utility:** It is imperative that the intrinsic utility and value of KNC continues to be enhanced on top of the current governance and liquidity mining use cases. Additional KNC utility ideas for KyberSwap.com under consideration include:

* Rewards/Raffles/NFT drops
* Boosted fees earned for LPs
* KNC ‘cashback’ as gas compensation for traders
* Time-based KNC staking rewards; the longer you stake your KNC, your address would hit certain milestones and get upgraded, enabling exclusive rewards in the future.

These are not set in stone and we welcome more ideas from the community to improve KNC token utility.

**Time-based KNC Conversion Cap:** KNC would be utilized as direct payment for marketing activities or liquidity pool seeding as much as possible. However, if KNC is required to be converted to stablecoins as payment to external parties, we would impose a suitable limit or emission rate for KNC that can be converted within a time period (e.g. a week or a month) in order to ensure token stability.

## Conclusion

We strongly believe that we can effectively utilize the remaining KNC in the ecosystem growth fund to drive adoption for KyberSwap.com and the KNC token itself. Burning KNC would only result in a short-term supply shock but does not support long-term value accrual.

On the other hand, effective utilization of KNC in upcoming initiatives could potentially result in more users, volume, and fees for LPs and KyberDAO voters. This would also increase the number of KNC holders who help expand the Kyber ecosystem, with the ability to stake KNC and vote.

KNC plays a valuable and central role in the Kyber ecosystem. KNC holders not only own a useful asset, but also a stake in DeFi’s liquidity infrastructure. We want to work closely with the community to ensure that KNC is utilized in the most efficient and impactful way possible and enhance its long-term value.