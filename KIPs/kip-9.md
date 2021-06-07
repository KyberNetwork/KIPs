---
kip: 9
title: Kyber DMM Expansion and Liquidity Mining on Polygon
status: Active
type: Mint KNC
authors: Kyber Network team
created: 2021-05-16
---

```
executor: long timelock executor
voting_power: current staked voting power
execution:
  1. transfer KNC proxy’s admin to 0x500180A94cB854e98770872AF4E4BB1dD67Af559
  2. mint 15138212 KNC to 0xe6a7338cba0a1070adfb22c07115299605454713 (the Dao Operator)
  3. mint 26912376 KNC to 0x41f5D722e6471c338392884088bD03340f50b3b5 (the short timelock executor)
start_timestamp: 1623136027 (Tuesday, June 8, 2021 07:07:07 GMT+00:00)
end_timestamp: 1623740827 (Tuesday, June 15, 2021 07:07:07 GMT+00:00)
```

## Summary

Given Polygon’s increasing popularity among DeFi users, and the ease with which Kyber DMM (Dynamic Market Maker) protocol can be deployed on their network, KIP-9 proposes the following:
1. The deployment of Kyber DMM on Polygon, with a portion of trading fees generated on Polygon going to KyberDAO. This complements the existing Kyber DMM deployment on Ethereum.
2. In addition, **6% of the 42M KNC minted for the Ecosystem Growth Fund, amounting to 2.52M KNC (~$5.5M)**, should be utilized as incentives to bootstrap liquidity and adoption on the Polygon-deployed Kyber DMM. This is an initial investment into the Polygon network that we believe will greatly benefit stakeholders in the Kyber ecosystem.
3. Making the necessary technical changes to the KyberDAO contracts to accommodate the initiatives stated above.


## Motivation

**For Kyber DMM deployment on Polygon**

Polygon has risen in popularity in 2021 with its mission to build a suite of scaling solutions and become Ethereum’s Internet of Blockchains infrastructure. As of May 21, 2021, roughly $6.5 billion of Ethereum and Ethereum-based tokens were locked within smart contracts on Polygon, and 356 projects and companies across 13 different verticals are building on Polygon’s ecosystem (source: [The Block](https://www.theblockcrypto.com/research/105540/mapping-out-polygons-ecosystem)).

Kyber’s vision is to deliver a sustainable liquidity infrastructure for DeFi, and this extends to the DeFi ecosystem on Polygon as well. We believe that Polygon is in need of an extremely capital efficient liquidity protocol to cater to its diverse ecosystem of Dapps and DeFi use cases and Kyber DMM can fulfil this important role. Kyber DMM would be able to empower Polygon liquidity providers with the ability to maximise the use of their capital, earning more fees with less capital compared to other platforms.

In addition, the high and volatile gas fees on Ethereum have pushed users to explore alternative systems such as Polygon for trading and other DeFi use cases. Similarly, the Kyber community has often requested for a cheaper trading and liquidity provision experience. 

Polygon presents a viable and attractive alternative for Kyber DMM users, with gas costs around a few cents compared to a few dollars on Ethereum, and the average block processing time is a couple of seconds compared to 12-15 seconds on Ethereum. Kyber DMM can also be quickly deployed on Polygon.

**For Liquidity Mining on Polygon**

Disbursing liquidity incentives has become standard practice for most major DeFi projects and has proven to be a useful tool to attract initial liquidity. A well-designed Kyber DMM liquidity mining campaign on Polygon can help:
*   **Bootstrap liquidity:** Additional liquidity incentives are necessary to attract more liquidity providers and total value locked (TVL) to Kyber DMM as soon as possible. Ideally, with the added bonus of liquidity incentives, Kyber DMM can be the most capital efficient and attractive venue in Polygon to add liquidity for the selected token pairs.
*   **Showcase Kyber DMM’s benefits to liquidity providers:** If they are incentivized to use the amplified pools, liquidity providers on Polygon will naturally learn about and enjoy the benefits of high capital efficiency and dynamic fees.
*   **Bring more DeFi participants and value into the Kyber ecosystem:** More liquidity providers using amplified pools would mean more of them receiving KNC rewards and becoming part of the Kyber ecosystem and community, with the ability to stake KNC and vote on the KyberDAO. This further decentralizes the governance of Kyber Network. By receiving KNC, liquidity providers also gain a stake in DeFi’s liquidity infrastructure.

The overall objective is to kickstart Kyber DMM’s presence on Polygon and take the first steps in building a sustainable and scalable liquidity infrastructure for the DeFi ecosystem there.

## Deploying Kyber DMM on Polygon 

If KIP-9 is approved, Kyber DMM will be deployed on the Polygon network and this deployment will become part of the overall Kyber liquidity hub. 10% of the collected fees (dynamic fees, differs with each pool) from trading activities on Polygon will be converted to KNC and transferred to KyberDAO on Ethereum via the Polygon-Ethereum bridge. 

KyberDAO will subsequently distribute fees as rewards to voters in accordance with the new fee system (to be determined in KIP-10). The entire process will be managed by the main KyberDAO multisig.

## Liquidity Mining on Polygon

We propose that 2.52M KNC (~$5.5M) be distributed across 6 eligible pools, with allocation focused on certain pools based on demand, asset scarcity, and other strategic requirements on Polygon.

**Proposed DMM Pools on Polygon**

| Pair      | AMP | Allocation (KNC) | Rationale for incentivizing the pool                                                                                                                                                                                                                                                                                                                                           |
|-----------|-----|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| KNC-ETH   | 1.9 | 327,000          | To enhance KNC liquidity and encourage KNC holders to lock up their tokens for a prolonged period to govern Kyber Network, liquidity incentives should be awarded to an amplified KNC-ETH pool on Polygon. This also acts as a natural counter against inflationary pressure.                                                                                                  |
| KNC-MATIC | 1.7 |  90,000          | Awarding liquidity incentives to an amplified KNC-MATIC pool on Polygon enhances liquidity for both the KNC and MATIC tokens and encourages holders to lock up their rewards from eligible liquidity mining pools, forming a natural counter against inflationary pressure. Creating a MATIC pool is also a natural step towards connecting the Kyber and Polygon communities. |
| MATIC-DAI | 1.5 |  56,000          | MATIC is the native token and a critical component of the Polygon ecosystem, with close to 100,000 token holders. Creating a MATIC pool is a natural step towards connecting the Kyber and Polygon communities.                                                                                                                                                                |
| USDC-ETH  | 1.6 | 955,000          | USDC-ETH is the most traded pair on Polygon. This would be a popular pool to hold USDC while maintaining exposure to ETH, and Kyber DMM is able to amplify liquidity by 1.6x in this pool.                                                                                                                                                                                     |
| USDC-USDT | 200 | 546,000          | Stablecoins pegged to the US Dollar such as USDT and USDC, are among the most traded and held tokens in DeFi and Polygon. Strongly correlated/stable pairs also provide the best showcase of the high capital efficiency possible on Kyber DMM.                                                                                                                                |
| USDC-DAI  | 200 | 546,000          | Stablecoins pegged to the US Dollar such as USDC and DAI, are among the most traded and held tokens on Ethereum. Strongly correlated/stable pairs also provide the best showcase of the high capital efficiency possible on Kyber DMM (amplified by 200x in this pool).                                                                                                        |

_*AMP = Amplification factor. Amplified pools have higher capital efficiency. Higher AMP, higher capital efficiency within a tighter price range._

## Other Technical Changes

To save execution time and improve contract configuration, we propose to cancel the execution of the earlier KIP-8 to make way for KIP-9. KIP-9 will include the execution of [KIP-8](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-8.md)’s relevant terms plus an additional configuration change:

*   Transfer the admin of KNC token from the Dao Long Executor to a smart contract called KNC Proxy Admin at 0x500180A94cB854e98770872AF4E4BB1dD67Af559. This admin contract has the Dao Long Executor as its owner and only gives write permission to the owner. At the same time, it shows the implementation address of the KNC proxy contract.

## On-chain execution

1. Transfer KNC proxy’s admin to 0x500180A94cB854e98770872AF4E4BB1dD67Af559
2. Mint 15,138,212 KNC and send to 0xe6a7338cba0a1070adfb22c07115299605454713 (the Dao Operator) for the liquidity mining programs
3. Mint 26,912,376 KNC and send to 0x41f5D722e6471c338392884088bD03340f50b3b5 (the Dao Short Executor) for future expenses

## Conclusion

We believe that deploying Kyber DMM on Polygon and utilizing KNC for a liquidity mining program are prudent investments that give Kyber a major foothold in an increasingly-popular Polygon network. Depending on the impact of the first liquidity mining program on Polygon, more KNC liquidity incentives may be proposed in the future.
Ultimately, through these initiatives, more Polygon users will hold KNC and get introduced to Kyber, thereby enlarging and enriching the Kyber ecosystem. This will in turn reap substantial benefits for Kyber stakeholders in the long run.
