---
kip: 27
title: Improving KNC Liquidity and Pair Diversity
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2023-10-10
---

---

campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: use KNC from 0x91c9D4373B077eF8082F468C7c97f2c499e36F5b (KyberDAO multisig) to add KNC liquidity to the chains and KNC pairs selected based on the voting result.
start_timestamp: 1696924800 (Tuesday, 10 Oct, 2023 3:00:00 PM GMT+7)
end_timestamp: 1697529600 (Tuesday, 17 Oct, 2023 3:00:00 PM GMT+7)
options: 1, 2, 3, 4
option_titles: "Avalanche - axlKNC-USDC, axlKNC-AVAX", "Base - KNC-USDC, KNC-ETH", "Linea - KNC-WBTC, KNC-USDT", "Scroll - KNC-USDC, KNC-ETH"
min_knc_voted_percentage: 40000000000000000 (4%)

---
## Summary

Improving KNC liquidity is a key element in ensuring stability for the token. Moreover, other external project tokens paired with KNC also benefit from this improved liquidity as their holders gain another trading market and an avenue to earn fees from their capital. As these tokens and KNC gain traction they help generate more volume and fees through KyberSwap.

We propose to further improve liquidity for KNC on KyberSwap as well as increase the type of tokens paired with KNC. KyberDAO ecosystem funds are finite and there are pros and cons to consider when it comes to adding funds to KNC-paired pools. As such, KyberDAO would be responsible for determining the KNC chains and pairs the additional funds would flow to.

As started in [KIP-21](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-21.md), a small portion of KNC from the KyberDAO ecosystem fund would be allocated to improving KNC liquidity.

KyberDAO will vote for its preferred chain (and suggested KNC-paired pools) that would receive priority for the funds, based on a list highlighted later in this proposal. For this KIP proposal, **100,000 KNC** would be allocated for liquidity enhancement for each KNC pair selected as part of the winning vote. 

KIP-27 was first proposed on the governance forum [here](https://gov.kyber.org/t/kip-27-improving-knc-liquidity-and-pair-diversity-discuss/2137).

## Motivation

- **Better KNC slippage and token stability:** Improved KNC liquidity means better slippage for KNC on KyberSwap and safeguards against market manipulation and massive price volatility during large trades. This becomes increasingly critical as KyberSwap expands into more chains and networks in DeFi and KNC liquidity is spread thin.
- **Increased utility for KNC:** New KNC pairs added would provide more choices for KNC holders to add token liquidity and earn fees, which is an important utility for KNC and would drive more adoption for the token. This is especially beneficial for KNC token holders who also own other types of tokens.
- **Enabling better portfolio management for KNC holders/traders:** Better liquidity enables more accurate and reliable market analysis and KNC holders/traders would be able to make more informed decisions regarding their portfolio management e.g. when hedging their KNC positions.
- **Deeper KNC insights:** By allowing KyberDAO to vote on which KNC chains and pairs get more liquidity, the community would have a direct influence on KNC liquidity and by extension KyberSwap’s volume performance and the fees collected for KyberDAO. The KyberSwap team would gain valuable insights on which chains and tokens are preferred by holders and users at the moment, and this can inform the team’s liquidity strategies moving forward.
- **More volume and fees for KyberSwap and KyberDAO:** In an ideal scenario, if suitable KNC pairs and chains are selected, it would result in more KyberSwap users and KNC holders, as well as higher volume, TVL (total value locked), and fees generated for liquidity providers and KyberDAO.
- **KNC exposure to other project communities:** When other project tokens are paired with KNC in KyberSwap liquidity pools, their holders and users have another avenue to swap their tokens against KNC or earn fees by adding their token liquidity. This helps bring more attention to KNC and KyberSwap. In addition, if partner projects want their tokens to be paired with KNC, they would have to submit proposals and rally community votes, increasing the chance of more KNC staked.

## **To Vote in KIP-27: KNC liquidity should be added/improved for which chain and pairs?**

For this KIP, the following chains and KNC pairs are currently being considered for improved liquidity. This is not an exhaustive list and it might change over time based on market conditions and liquidity needs.

From the list of options below, vote for your **most preferred chain** and its corresponding KNC pairs. Voting for a particular chain means you are voting for its 2 corresponding KNC pairs displayed.

**100,000 KNC** would be allocated per KNC pair. All pairs would be using a 1-2% fee tier with full price range unless stated otherwise. 

Priority is based on the percentage of votes received. The option that receives the highest voting percentage would get the highest priority, followed by the option with the next highest voting percentage and so on.

**Voting Options (select 1 option)**

| Chain | Suggested KNC Pair |
| --- | --- |
| Avalanche | axlKNC-USDC, axlKNC-AVAX |
| Base | KNC-USDC, KNC-ETH |
| Linea | KNC-WBTC, KNC-USDT |
| Scroll | KNC-USDC, KNC-ETH |

*Note: Ethereum, Polygon, Optimism, Arbitrum, and BNB are omitted from this voting round as they were already voted on in [KIP-21](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-21.md) and [KIP-24](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-24.md), and the focus is on the recently deployed networks. Polygon zkEVM is omitted as there is already starting liquidity for major KNC pairs. zkSync Era is omitted as it is unable to support Elastic pools at the moment. Avalanche is included due to the need for Axelar’s axlKNC after Multichain ceased operations (affecting the practical use of Multichain KNC).*

## **Voting Considerations**

Despite the clear benefits, it is important to be aware of the tradeoffs when it comes to improving liquidity for KNC pairs. KyberDAO members need to consider the following implications when casting their vote.

- **Small, short-term market impact on KNC:** Adding more KNC liquidity means converting a portion of KNC to the other paired token. For example, selling KNC to MATIC in a KNC-MATIC pool on Polygon; the market needs to be able to absorb the selling pressure and KyberDAO would bear the risks of holding this MATIC position as a liquidity provider. Note that this would be a reasonably small amount (~50% of 100,000 KNC to be converted to another token per pair selected in each KIP).
- **High volume and brand awareness:** Assuming the same fee tier, KyberDAO's ability to accurately select a suitable high volume chain and KNC pair would yield more direct fees and voter rewards. Conversely, a relatively lower volume chain and KNC pair selected might yield less direct fees and voter rewards. However, if the project token paired with KNC is reputable and well known, it is possible that more users from the other project start using KyberSwap and join our community. This could result in more users and volume for KyberSwap in the long run.
- **Liquidity concentration on different chains:** The chain on which new KNC liquidity is added would enjoy better rates and volume for KNC and potentially gain more KNC holders. As such, it is important for KyberDAO to consider which chain should be prioritized for fresh KNC liquidity funding. KyberDAO also has to take into account that within each chain, some KNC pairs possess more liquidity than others.

**Current KNC pairs already on KyberSwap (03/10/2023)**

| Chain | KNC Pair |
| --- | --- |
| Avalanche | 0 |
| Base | 0 |
| Linea | KNC-ETH, KNC-axlKNC |
| Polygon zkEVM | KNC-USDC, KNC-MATIC |
| Scroll | Scroll mainnet not live yet |

## **Important Safeguards**

- **Maintaining secure and optimized liquidity positions:** The KyberSwap team would be responsible for managing the pool setup and operations, and ensure the security of funds. The associated fee tier for the KNC-paired pool would be 1-2% (depends on market conditions) with full price range unless stated otherwise by the KyberSwap team. Once the pools for selected KNC pairs are set up, rebalancing, adding or removing liquidity would be at the team’s discretion and acts as a safeguard against unforeseen market events and price volatility. For example:
    - Adverse market conditions for either token in a pair might require rebalancing to optimize liquidity positions.
    - Sudden critical technical problems faced by a chain might require immediate removal of liquidity on that chain.
- **Preventing overconcentration of liquidity:** It is recommended that KNC chains and pairs that received the winning votes in the previous voting rounds ([KIP-21](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-21.md) and [KIP-24](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-24.md)) be omitted from the current list of options, so as to prevent an overconcentration of liquidity on a particular chain or pair.

## **For External Projects: Apply for token to be paired with KNC**

It would be ideal to have a wider variety of popular project tokens paired with KNC. External projects that would like their tokens to be paired with KNC can reach out to the KyberSwap team and submit proposals to the KyberDAO forum at: https://gov.kyber.org/c/collaborations/knc-pair/30

The following format should be used in the submission:

- Proposal title: [Project Name] Add KNC pair for [insert token] on KyberSwap
- Project name:
- Token ticker:
- Token smart contract address:
- Brief project background:
- Which chain KNC-paired liquidity should be added on:
- Why your token should be paired with KNC:
- Project website:
- Project Twitter:
- Contact information (Telegram/Discord/Twitter/Email):

If the proposed token pair is approved as a voting option in the next KIP, projects can proceed to rally the community to vote for them.

## Conclusion

Effectively utilizing a portion of the KNC in the KyberDAO ecosystem fund to improve KNC liquidity and increase the variety of pairs on key chains would yield substantial benefits for both KyberSwap and the KNC token in the long run.

KNC holders who stake and vote as part of KyberDAO now play a very important role in determining where and how KNC liquidity is improved, and this in turn affects the growth of KyberSwap and the fees earned by KNC voters. We want to work closely with the community to ensure that KNC liquidity gets improved in the most efficient and impactful way possible.