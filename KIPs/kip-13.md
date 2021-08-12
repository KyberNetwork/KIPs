---
kip: 13
title: Use B.Protocol v2 as a liquidation engine for the Kyber Network's fee liquidation framework
status: Draft
type: Configuration
authors: Dr. F
created: 2021-08-12
---

```
executor: long timelock executor
voting_power: current staked voting power
execution: TBD
start_timestamp: TBD
end_timestamp: TBD
```

## Summary
[KIP-11](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-11.md) deployed a framework for fee liquidations, namely to convert the protocol fees to KNC before distributing them to the DAO members.
KIP-13 propose to use B.Protocol as the liquidation engine, and to list the liquidation engine as a reserve in Kyber Network.


## Motivation
B.Protocol v2 implements a novel and fully decentralized [algorithm](https://docs.bprotocol.org/technical-documentation/untitled-1) for inventory sell. The algorithm is already live with our [Liquity integration](https://docs.bprotocol.org/info/user-guides/liquity-user-guide) and manage over $30m of users' deposits.
In the core of the protocol resides a smart contract formula that price inventory according to an imbalance parameter and market price.
Using B.Protocol will offer the following benefits:
1. **Better (expected) execution price:** Kyber's current liquidation system offer a fixed discount in order to incentives keepers to perform the liquidation. With B.Protocol the discount varies according to the inventory imbalance, and will be on average much lower.
In addition Kyber's current liquidation system executes the trade as a taker, while in B.Protocol the inventory is being sold as maker orders. 

2. **Better contribution to the Kyber Network DEX:** The current system encourage short term arbitrage bots to participate in the trade, while B.Protocol v2, as a reserve in Kyber, will offer, during the liquidation process, non arbitrage prices, which would benefit real users who will enjoy better trade price.

3. **Fully distributed and incentive compatible:** The current system relies on bot operators, and the incentive for the bot operators comes on the expense of the DAO profits.

## System Overview
B.Protocol's automatic market maker (B.AMM) will be deployed and will offer token=>ETH and ETH=>KNC pairs.
Kyber's DAO will control the B.AMM price oracle, and B.Protocol's DAO will control the imbalance factor and the rebalance fee (capped by an agreed value).

Whenever fees are accumulated at the Kyber's treasury, they will be priced for sale in return to ETH by the B.AMM, which will be a reserve at kyber network.
Whenever ETH is accumulated it will be offered for sale in return to KNC in the same way.
Whenever KNC is accumulated it will be automatically be transfered to the Kyber's DAO.

Chainlink keeper service will be deployed to automatically convert LP tokens into their original underlying tokens.

Technical details about the B.AMM along with the original whitepaper could be found [here](https://docs.bprotocol.org/technical-documentation/untitled-1).

## Implementation
TODO

## Onchain execution

TODO

## Conclusion
This fee liquidation framework could greatly benefit by adopting the B.Protocol's B.AMM. It could potentially increase Kyber DAO's profit, could help improving the value proposition to its users (rather than the existing mechanism which only improves arbitrage bots) and can help fight MEV and be more incentive compatible w.r.t current implementation.

