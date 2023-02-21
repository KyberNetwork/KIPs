---
kip: 21
title: Improving KNC Liquidity and Pair Diversity
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2023-02-15
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: use KNC from 0x91c9D4373B077eF8082F468C7c97f2c499e36F5b (KyberDAO multisig) to add KNC liquidity to the chains and KNC pairs selected based on the voting result.
start_timestamp: 1677574800 (Tuesday, February 28, 2023 4:00:00 PM GMT+7)
end_timestamp: 1678179600 (Tuesday, March 7, 2023 4:00:00 PM GMT+7)
options: 1, 2, 3, 4, 5, 6
option_titles: "Ethereum - KNC-USDC, KNC-WBTC ", "Polygon - KNC-MATIC, KNC-WBTC", "Arbitrum - KNC-USDC, KNC-WBTC", "Optimism - KNC-USDC, KNC-WBTC", "Avalanche - KNC-USDC, KNC-WBTC", "BNB chain - KNC-BNB, KNC-USDT"
min_knc_voted_percentage: 30000000000000000

```

## Summary

Improving KNC liquidity is a key element in ensuring stability for the token. Moreover, other external project tokens paired with KNC also benefit from this improved liquidity as their holders gain another trading market and an avenue to earn fees from their capital. As these tokens and KNC gain traction they help generate more volume and fees through KyberSwap.

We are proposing to further improve liquidity for KNC on KyberSwap as well as increase the type of tokens paired with KNC. KyberDAO ecosystem funds are finite and there are pros and cons to consider when it comes to adding funds to KNC-paired pools. As such, KyberDAO would be responsible for determining the KNC chains and pairs the additional funds would flow to.

Every 4 epochs (~2 months), a small portion of KNC from the KyberDAO ecosystem fund (~19,868,149.25 KNC currently remaining in the fund) would be allocated to improving KNC liquidity, focusing first on Ethereum, Polygon, Arbitrum, Optimism, Avalanche, and BNB Chain. 

KyberDAO will vote for its preferred chains (and suggested KNC-paired pools) that would receive priority for the funds, based on an initial list highlighted later in this proposal. For this KIP proposal, **100,000 KNC** would be allocated for liquidity enhancement for each KNC pair selected as part of the winning vote.

## Motivation

- **Better KNC slippage and token stability:** Improved KNC liquidity means better slippage for KNC on KyberSwap and safeguards against market manipulation and massive price volatility during large trades. This becomes increasingly critical as KyberSwap expands into more chains and networks in DeFi and KNC liquidity is spread thin.
- **Increased utility for KNC:** New KNC pairs added would provide more choices for KNC holders to add token liquidity and earn fees, which is an important utility for KNC and would drive more adoption for the token. This is especially beneficial for KNC token holders who also own other types of tokens.
- **Enabling better portfolio management for KNC holders/traders:** Better liquidity enables more accurate and reliable market analysis and KNC holders/traders would be able to make more informed decisions regarding their portfolio management e.g. when hedging their KNC positions.
- **Deeper KNC insights:** By allowing KyberDAO to vote on which KNC chains and pairs get more liquidity, the community would have a direct influence on KNC liquidity and by extension KyberSwap’s volume performance and the fees collected for KyberDAO. The KyberSwap team would gain valuable insights on which chains and tokens are preferred by holders and users at the moment, and this can inform the team’s liquidity strategies moving forward.
- **More volume and fees for KyberSwap and KyberDAO:** In an ideal scenario, if suitable KNC pairs and chains are selected, it would result in more KyberSwap users and KNC holders, as well as higher volume, TVL (total value locked), and fees generated for liquidity providers and KyberDAO.
- **KNC exposure to other project communities:** When other project tokens are paired with KNC in KyberSwap liquidity pools, their holders and users have another avenue to swap their tokens against KNC or earn fees by adding their token liquidity. This helps bring more attention to KNC and KyberSwap. In addition, if partner projects want their tokens to be paired with KNC, they would have to submit proposals and rally community votes, increasing the chance of more KNC staked.

## Proposed Plan for KNC Liquidity Injection

Every 4 epochs (~2 months), selected KNC-paired pools would receive **100,000 KNC worth of liquidity** each. We would like KyberDAO to vote (via an on-chain KIP) for which chains and their corresponding KNC pairs would receive priority for this fresh liquidity injection. We are currently focusing activities on: Ethereum, Polygon, Arbitrum, Optimism, Avalanche, and BNB chain.

In each KIP, KyberDAO voters can vote for one or more chains (and by extension the corresponding KNC pairs suggested for the chains) to receive KNC liquidity. 

The chain that receives the highest % of votes in the KIP would get the highest priority. Subsequent chains and pair/s would also be selected based on the % of KNC votes received. For example, the chain that received the 2nd highest vote will be prioritized next, followed by the 3rd highest etc.

The KNC amount and focus chains may be revised over time based on community feedback.

Expected voting months in 2023 for this KIP category:
- February
- April
- June
- August
- October
- December

**Note:** For edge cases where an external project requires KNC-related liquidity within a very short period of time, a KIP may be submitted that focuses on that particular project. In such a scenario, the KIP could be a binary YES/NO vote. For example, instead of voting from a list of KNC pair options, KyberDAO may have a proposal to vote YES/NO on whether to accept a particular KNC-Token pair or YES/NO on whether additional KNC liquidity should be added to a cross-chain bridge.

### To Vote in KIP-21: KNC liquidity should be added/improved for which chain and pairs?

For this KIP, the following chains and KNC pairs are currently being considered for improved liquidity. This is not an exhaustive list and it might change over time based on market conditions and liquidity needs.

From the list of options below, vote for **one or more** of your preferred chains and their corresponding KNC pairs. By default, voting for a particular chain means you are voting for its 2 corresponding KNC pairs displayed. 

**100,000 KNC** would be allocated per KNC pair. All pairs would be using a 1% fee tier with full price range unless stated otherwise. The option that receives the highest number of votes would get the highest priority. For this KIP, we intend to select the top 2 chains (and the corresponding KNC pairs) with the highest voting percentages.

**KIP-21 Voting Options**

|Chain|Suggested KNC Pair|
| --- | --- |
|Ethereum|KNC-USDC, KNC-WBTC|
|Polygon|KNC-MATIC, KNC-WBTC|
|Arbitrum|KNC-USDC, KNC-WBTC|
|Optimism|KNC-USDC, KNC-WBTC|
|Avalanche|KNC-USDC, KNC-WBTC|
|BNB Chain|KNC-BNB, KNC-USDT|

## Voting Considerations

Despite the clear benefits, it is important to be aware of the tradeoffs when it comes to improving liquidity for KNC pairs. KyberDAO members need to consider the following implications when casting their vote.

- **Small, short-term market impact on KNC:** Adding more KNC liquidity means converting a portion of KNC to the other paired token. For example, selling KNC to MATIC in a KNC-MATIC pool on Polygon; the market needs to be able to absorb the selling pressure and KyberDAO would bear the risks of holding this MATIC position as a liquidity provider. Note that this would be a reasonably small amount (~50% of 100,000 KNC to be converted to another token per pair selected in each KIP).
- **High volume and Brand awareness:** Assuming the same fee tier, KyberDAO's ability to accurately select a suitable high volume chain and KNC pair would yield more direct fees and voter rewards. Conversely, a relatively lower volume chain and KNC pair selected might yield less direct fees and voter rewards. However, if the project token paired with KNC is reputable and well known, it is possible that more users from the other project start using KyberSwap and join our community. This could result in more users and volume for KyberSwap in the long run.
- **Liquidity concentration on different chains:** The chain on which new KNC liquidity is added would enjoy better rates and volume for KNC and potentially gain more KNC holders. As such, it is important for KyberDAO to consider which chain should be prioritized for fresh KNC liquidity funding. KyberDAO also has to take into account that within each chain, some KNC pairs possess more liquidity than others.

**Current KNC pairs already on KyberSwap (20/01/2023)**
|Chain|KNC Pair|
| --- | --- |
|Ethereum|KNC-ETH, KNC-LINK|
|Polygon|KNC-MAI, KNC-LDO, KNC-AAVE, KNC-ETH, KNC-LINK, KNC-USDC, KNC-USDT (low liquidity)|
|Arbitrum|KNC-ETH, KNC-LINK, KNC-LDO, KNC-mKNC, mKNC-MAI|
|Optimism|KNC-ETH, KNC-OP, KNC-LDO, KNC-AAVE, KNC-SNX, KNC-mKNC, mKNC-MAI, KNC-FRAX (low liquidity)|
|Avalanche|KNC-WETH.e, KNC-LINK.e, KNC-AAVE.e, KNC-MAI|
|BNB Chain|KNC-BNB, KNC-ETH, KNC-USDT (low liquidity on all 3 pairs)|

## Important Safeguards

- **Maintaining secure and optimized liquidity positions:** The KyberSwap team would be responsible for managing the pool setup and operations, and ensure the security of funds. The associated fee tier for the KNC-paired pool would be 1% with full price range unless stated otherwise by the KyberSwap team. Once the pools for selected KNC pairs are set up, rebalancing, adding or removing liquidity would be at the team’s discretion and acts as a safeguard against unforeseen market events and price volatility. For example:
    - Adverse market conditions for either token in a pair might require rebalancing to optimize liquidity positions.
    - Sudden critical technical problems faced by a chain might require immediate removal of liquidity on that chain.
- **Preventing overconcentration of liquidity:** The KNC chain and pairs that receive the winning vote in the latest voting round would be omitted from the list of options in the next round, so as to prevent an overconcentration of liquidity on a particular chain or pair.

## For External Projects: Apply for token to be paired with KNC

It would be ideal to have a wider variety of popular project tokens paired with KNC. External projects that would like their tokens to be paired with KNC can reach out to the KyberSwap team and submit proposals to the KyberDAO forum at: [https://gov.kyber.org/c/collaborations/knc-pair/30](https://gov.kyber.org/c/collaborations/knc-pair/30)

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