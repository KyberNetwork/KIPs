---
kip: 13
title: KyberDMM Expansion and Liquidity Mining on Avalanche
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2021-08-25
---

```
executor: short timelock executor
voting_power: current staked voting power
execution: transfer 3M KNC to 0xD69D7A1031e6E63a162414F9A77278757690C30E (kyber multisig to handle KNC bridging between ethereum and other chains)
start_timestamp: 1629896400 (Wed Aug 25 2021 13:00:00 UTC)
end_timestamp: 1630393627 (Tue Aug 31 2021 07:07:07 UTC)

```
## Summary

[Avalanche](https://www.avax.network/) is an open, programmable smart contracts platform that is starting to be a popular venue for DeFi Dapps and NFTs due to its high throughput and fast transaction finality.

Avalanche Foundation is proposing that the [KyberDMM (Dynamic Market Maker)](https://dmm.exchange/#/about) protocol be deployed on Avalanche, coupled with a joint liquidity mining campaign. We believe this is aligned with Kyber Network’s aim to widen adoption across different networks beyond Ethereum. Since Kyber’s vision is to deliver a sustainable liquidity infrastructure for DeFi, this should also extend to Avalanche’s DeFi ecosystem. We had a [forum discussion](https://gov.kyber.org/t/kyberdmm-deployment-and-joint-liquidity-mining-on-avalanche/315) on this topic and received strong support for this KIP.

The following is being proposed:
1. The deployment of KyberDMM protocol and the creation of amplified liquidity pools on Avalanche.
2. **$3M worth of KNC from Kyber’s ecosystem fund** to be utilized as incentives to bootstrap   liquidity and adoption of KyberDMM on Avalanche. In return, Avalanche Foundation will contribute **$2M worth of AVAX tokens** as incentives.
3. Avalanche Foundation and Kyber to work together on a joint liquidity mining and marketing campaign to educate users on the benefits of both projects.

Separately, *Kyber is encouraged to collaborate with other Avalanche-based projects to create liquidity pools and run additional liquidity mining campaigns* to amplify the impact of the launch.

## Motivation

**Why KyberDMM should deploy on Avalanche** 

The high and volatile gas fees on Ethereum and other chains have sometimes resulted in a poor DeFi user experience. Avalanche provides an attractive venue for users that want a cheaper and faster experience when it comes to DeFi use cases such as trading, liquidity provision, and lending/borrowing.

Avalanche has smart contract functionality and is Solidity and Ethereum Virtual Machine (EVM)-compatible, allowing existing Dapps on Ethereum to be easily ported over to Avalanche using familiar tooling. Ethereum assets can also be easily migrated via the Avalanche Bridge. Kyber will be in good company, as many popular Ethereum projects such as Aave will soon be launching on Avalanche.

If KyberDMM is deployed on Avalanche, it would also be the `first dynamic market maker protocol on Avalanche` that enables liquidity providers to maximise their capital by achieving high capital efficiency for any token pair (not just stablecoins) while allowing traders to enjoy minimal slippage.

**Why Run a Joint Liquidity Mining Campaign**

Liquidity incentives have proven to be crucial in attracting initial liquidity on a new network. 
A well-designed liquidity mining campaign between Kyber and Avalanche can help:
* Bootstrap liquidity for key token pairs
* Showcase KyberDMM’s benefits of high capital efficiency and dynamic fees to liquidity providers
* Bring more DeFi participants and value into both the Avalanche and Kyber ecosystems

Overall, this will kick start KyberDMM’s role on Avalanche and help Kyber take the first steps in building a sustainable and scalable liquidity infrastructure there.

## Liquidity Mining on Avalanche

We propose that *$3M worth of KNC and $2M worth of AVAX* be distributed over 2 months for liquidity providers of participating pools. At least one of the participating pools should have an AVAX pair. 

`Campaign duration: 2 months`

`Vesting period per harvest: 14 days`

The following pools are proposed:

* USDT-DAI (AMP=400)
* AVAX-ETH (AMP=1.5)
* AVAX-DAI (AMP=1.5)
* WBTC-ETH (AMP=2)
* KNC-AVAX (AMP=1.5)
* KNC-ETH (AMP=1.9)

## Conclusion

Deploying KyberDMM on Avalanche and utilizing KNC for liquidity mining initiatives would be a good strategy to give Kyber a major foothold on Avalanche. Through these initiatives, we expect more users to hold AVAX and KNC and learn about Avalanche and Kyber, thereby enlarging and enriching both ecosystems.