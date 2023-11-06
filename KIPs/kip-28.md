---
kip: 28
title: KyberDAO to open a Limit Order for mKNC holders to swap mKNC to KNC
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2023-11-03
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: use KNC from DAO to open a KyberSwap limit order to swap for mKNC on affected chains
start_timestamp: 1699344000 (Tuesday, November 7, 2023 3:00:00 PM GMT+7)
end_timestamp: 1699948800 (Tuesday, November 14, 2023 3:00:00 PM GMT+7)
options: 1, 2
option_titles: "Yes", "No"
min_knc_voted_percentage: 40000000000000000 (4%)

```
## Summary

Multichain previously bridged and deployed KNC on Avalanche, Arbitrum, Optimism, and Fantom. This Multichain-deployed version of KNC is using the AnyswapV5ERC20 contract, and has been labeled as “mKNC” on [KyberSwap.com](http://KyberSwap.com).

Multichain [ceased all operations](https://twitter.com/MultichainOrg/status/1679768407628185600?s=20) on 14 July 2023, following which mKNC holders were not able to use the Multichain user interface (UI) or contracts to bridge back and receive KNC on their original source chain.

There are a total of 192,067.31533 mKNC (~$144,050) held across the following 4 chains.

1. [Avalanche](https://snowtrace.io/token/0x39fc9e94caeacb435842fadedecb783589f50f5f#code): 1,439 addresses holding 174,198.587308 KNC
2. [Arbitrum](https://arbiscan.io/token/0x316772cFEc9A3E976FDE42C3Ba21F5A13aAaFf12): 95 addresses holding 15,870.169533 KNC
3. [Optimism](https://optimistic.etherscan.io/token/0x4518231a8FDF6ac553B9BBD51Bbb86825B583263#code): 47 addresses holding 1,965.323489 KNC
4. [Fantom](https://ftmscan.com/token/0x1e1085efaa63edfe74aad7c05a28eae4ef917c3f): 4 addresses holding 33.235 KNC

The KyberSwap team have been exploring various means to help users who are currently affected by the Multichain situation and still hold mKNC.

In this KIP, we propose a solution that would enable affected users to switch (swap) their mKNC to a suitable version of KNC on the affected chain, using KyberSwap’s Limit Order feature.

KNC would be sourced from the [KyberDAO ecosystem fund](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-23.md), under the “Trading and Liquidity Growth” allocation.

This KIP was first proposed on the governance forum [here](https://gov.kyber.org/t/kip-28-draft-kyberdao-to-open-a-limit-order-for-mknc-holders-to-swap-mknc-to-knc-discuss/2170).

## Motivation

Immediately after determining that Multichain was likely to cease operations, KyberSwap stopped all farms associated with Multichain-deployed KNC contracts and warned users multiple times not to use or interact with these contracts on Avalanche, Arbitrum, Optimism, and Fantom.

Unfortunately, some users still failed to convert their mKNC to suitable versions of KNC before the Multichain bridge became inactive. We then sought assistance from the Multichain team to reinstate their bridge UI or unlock the KNC residing in the bridge wallets, but we were informed that this is currently not possible.

As a gesture of goodwill and appreciation for our users, we would like to propose that KyberDAO provide the funds and the means to help them switch out their mKNC for a suitable version of KNC on the affected chain. We would be one of the few projects in DeFi that is taking concrete steps to help users affected by the Multichain situation. In addition, we aim to turn this problem into an opportunity to showcase the merits of using KyberSwap’s [Limit Order feature](https://docs.kyberswap.com/kyberswap-solutions/limit-order).

## Proposed Plan

**Set up a Limit Order on each chain for users to switch mKNC to KNC**

If this KIP is approved, KyberDAO would prepare 192,067.31533 KNC (same amount of mKNC held by users) from the ecosystem fund to be exchanged via 4 different Limit Orders on Avalanche, Arbitrum, Optimism, and Fantom; each order based on the corresponding mKNC amount residing on the affected chain.

**Key Steps**

* On each affected chain, we create a Limit Order that allows users to swap mKNC to a suitable version of KNC, facilitated by KyberSwap aggregator. As users swap their mKNC to KNC, the Limit Order gets partially filled until the full order (maximum KNC allocated for the chain) has been swapped, or until the expiry date. The Limit Order will be open for a period of 2 months, following which it would expire and users would lose the opportunity to swap mKNC to KNC on that chain. Advance notice would be given regarding the creation date of the Limit Order.
* This process would be done sequentially chain-by-chain, with a small buffer time in between; to be completed first on Arbitrum, followed by Optimism, Fantom, and lastly Avalanche.
* The Limit Order created would set the exchange rate for mKNC to KNC at 1:1. However, a minor fee could be applied according to the [Limit Order fee structure](https://docs.kyberswap.com/kyberswap-solutions/limit-order/developer-guides/fill-limit-order#limit-order-protocol-fees).
* In exchange for KNC, KyberDAO would keep the mKNC switched out by users.

## Important Considerations

This prevailing mKNC problem was born out of the sudden and unforeseen sunsetting of the Multichain bridge. As such, KyberSwap and KyberDAO are not obliged to compensate holders. However, the team understands the inconvenience and pain suffered by affected mKNC holders, and hopes the community can work together through this Limit Order initiative to soften the blow.

**Possible scenarios after users switch mKNC to KNC via KyberSwap Limit Order**

**Scenario 1:** Multichain’s operations are permanently ceased, the KNC in their bridge wallets on [BNB Chain](https://bscscan.com/token/0xfe56d5892bdffc7bf58f2e84be1b2c32d21c308b?a=0x5650c49d662cb83666ab0fad224453b603179d2a), [Polygon](https://polygonscan.com/token/0x1c954e8fe737f99f68fa1ccda3e51ebdb291948c?a=0x9ee45adbb2f2083ab5cd9bc888c77a662dbd55fe), and [Ethereum](https://etherscan.io/address/0x7beb05cf5681f402e762f8569c2fc138a2172978) are “burnt” forever, and the mKNC token remains unusable for any practical use case. After the Limit Order exchange on KyberSwap to convert their mKNC, users would be able to sell the KNC they received; this might result in some selling pressure. KyberDAO would be left holding the unusable mKNC.

**Scenario 2:** Multichain becomes active again and bridge contracts work the same way as before. KyberDAO uses Multichain to bridge mKNC back to KNC on Binance, Polygon etc. In other words, KNC “locked” in the Multichain bridge wallets can be retrieved by KyberDAO in exchange for mKNC (which KyberDAO would keep after the Limit Order exchange with users).

**Scenario 3:** Multichain team (or whoever controls their private keys) manually sells all the KNC in their bridge wallets and keeps the proceeds; this might result in some selling pressure. This would be beyond our control, whether or not we help users switch mKNC to KNC now.

**Scenario 4:** Multichain team transfers all the KNC in their bridge wallets back to addresses that hold mKNC on different chains. Since KyberDAO would keep mKNC from users (after the Limit Order exchange), KyberDAO wallets can receive the KNC released by Multichain.

**Scenario 5:** Multichain team transfers all the KNC in their bridge wallets back to addresses that had previously bridged KNC using Multichain contracts in the past. Affected users who had received KNC from KyberDAO (after the Limit Order exchange) would receive this extra KNC, which might be perceived as unfair. KyberDAO gets nothing and mKNC would remain unusable.

**Scenario 6:** Users who do not hold mKNC might attempt to purchase mKNC at a lower price before converting it to KNC using the Limit Order exchange. But the likelihood of this is very low as there is no liquidity for mKNC on KyberSwap pools.

## Conclusion

KyberDAO would consider the implications and vote on whether to proceed with this Limit Order initiative to help affected mKNC holders swap their tokens to a suitable version of KNC.

Our team would like to remind and warn users again that they should no longer use or interact with the Multichain-deployed (mKNC) token contracts on Avalanche, Arbitrum, Optimism, and Fantom.

* On the [KyberSwap.com](http://KyberSwap.com) UI, known Multichain-deployed KNC contracts are labelled as “mKNC” to clearly differentiate from KNC deployed using the chain foundation’s canonical/official bridge and other cross-chain bridges.
* KyberSwap [docs](https://docs.kyberswap.com/governance/knc-token/knc-contract-addresses#avalanche-chainid-43114) now state that using Multichain-deployed KNC is highly discouraged and not advisable.
* Explorers such as [Snowtrace](https://snowtrace.io/address/0x39fc9e94caeacb435842fadedecb783589f50f5f), [Avascan](https://avascan.info/blockchain/c/token/0x39fC9e94Caeacb435842FADeDeCB783589F50f5f), [Arbiscan](https://arbiscan.io/token/0x316772cFEc9A3E976FDE42C3Ba21F5A13aAaFf12), [Optimistic.etherscan](https://optimistic.etherscan.io/token/0x4518231a8FDF6ac553B9BBD51Bbb86825B583263#code), and [Ftmscan](https://ftmscan.com/token/0x1e1085efaa63edfe74aad7c05a28eae4ef917c3f) have added warning labels to inform users that the affected token contracts were bridged via Multichain. Social links and other associations with KyberSwap have also been removed on the explorers.
