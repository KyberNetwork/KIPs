---
kip: 16
title: Joint LM with DeFi Warrior, Jarvis Network and Ape In
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2021-09-13
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: transfer requested KNC to 0xD69D7A1031e6E63a162414F9A77278757690C30E (kyber multisig to handle KNC bridging between ethereum and other chains) depends on voting result.
start_timestamp: 1631603227 (Tue, 14 Sep 2021 07:07:07 UTC)
end_timestamp: 1631948827 (Tue, 18 Sep 2021 07:07:00 UTC)
options: 1, 2, 3, 4
option_titles: "DeFi Warrior", "Jarvis", "Ape In", "None"
min_knc_voted_percentage: 30000000000000000

```

## Summary

Based on forum discussions, the Kyber community is proposing that the following projects be included in the `Rainmaker` Joint Liquidity Mining program:

1. DeFi Warrior(FIWA) chain on BSC, for [FIWA-USDT](https://gov.kyber.org/t/joint-liquidity-mining-defiwarrior-fiwa-token-on-kyberdmm/421)

2. Jarvis Network on Polygon, for [jEUR-USDC, jGBP-USDC, jCHF-USDC and AUR-USDC](https://gov.kyber.org/t/joint-lm-with-jarvis-network-for-incentivizing-forex-pools/372/18).

3. Ape In on Avalanche, for [APEIN-WAVAX](https://gov.kyber.org/t/joint-liquidity-mining-on-avalanche-with-apein-on-kyberdmm/438).

## DeFi Warrior(FIWA)

### Project Introduction

DeFi Warrior is a DeFi x NFT Play2earn Blockchain game with a fascinating crypto galaxy game story. While NFT games are creating a strong trend, DeFi Warrior stands out with the combination of DeFi and NFT in the game, along with the story of the crypto world in miniature. In DeFi Warrior, each blockchain is a planet, and each crypto is a warrior. The planet is also the place where warriors can build their coin mining factory, and fight against bosses or enemies for rewards.

### Proposal Summary, Motivation, and Key Details

DefiWarrior is proposing a joint liquidity mining program with Kyber to help improve liquidity for the Fiwa token on KyberDMM protocol.

During the campaign period, liquidity providers who add liquidity (deposit tokens) on the eligible FIWA-USDT pool will receive LP tokens that can be staked on the Yield page for additional `FIWA and KNC` token rewards. As part of the campaign launch, there will also be joint marketing efforts with Kyber Network.

Additional Idea: Top 500 FIWA product users can claim a fixed KNC reward on KyberDMM immediately after they provide liquidity.

DefiWarrior is an ideal candidate for Rainmaker Liquidity Mining on KyberDMM. Key reasons:
 
- There has been high volume for the FIWA token for the past 30 days as seen on CoinGecko here.
- DefiWarrior as a GameFi project has been gaining a lot of traction and social users . The fiwa product has been widely used by hundreds of users and has been audited by Hacken .
- There are over 200,000 members in the DefiWarrior community and many are liquidity providers.DefiWarrior has integrated KyberDMM hence many DefiWarrior users are also indirect KyberDMM users. 

DefiWarrior will provide the minimum requirement of $200,000 worth of liquidity on a new amplified `FIWA-USDT (AMP=1.1)` pool on KyberDMM. Together with requested KNC rewards, total incentives exceed the minimum requirement of $200,000.


| KNC requested | Project contribution | Token pair | Vesting Schedule |Campaign duration|
|---------------|----------------------|------------|------------------|-----------------|
| $100,000       |$200,000             |FIWA-USDT   |14 Days           |2 Months         |


## Jarvis Network

### Project Introduction

Jarvis Network is a set of DeFi protocols to make DeFi more accessible. Synthereum is our first protocol. It allows the issuance and exchange without slippage of synthetic fiat currencies (aka jFIAT) like jEUR, jCHF or jGBP. It is live on Ethereum and Polygon.

The jFIATs are backed by USDC, with a collateral ratio of 125% and a liquidation threshold set at 105%. They are integrated in a 0-fee fiat on and off-ramp on both networks. They can be exchanged without slippage for USDC or for any other jFIAT on the Jarvis Exchange, leveraging from the minting and burning mechanism of the protocol: when a user wants to buy jFIAT, a liquidity pool holding USDC mints and sells them in the same transaction, at the Chainlink price feed; when a user wants to sell jFIAT, a liquidity pool buys them back and burn them to redeem their collateral in USDC.

From an end-user point of view, they buy or sell jFIAT without slippage. Thanks to this design, traders can perform arbitrage between this primary market and secondary markets such as AMMs, in order to maintain a strong peg.

### Proposal Summary, Motivation and Key Details

Jarvis Network is proposing a joint liquidity mining program with Kyber to help improve liquidity for the jFIATs token on KyberDMM protocol, and request to receive the KNC token upfront to add them to our LM contract.

During the campaign period, liquidity providers who add liquidity on the eligible jEUR-USDC, jGBP-USDC and jCHF-USDC amplified liquidity pools will receive LP tokens that can be staked on the yield page, and/or on our own Yield application, for additional `JRT, UMA and KNC` token rewards, depending on the outcome of the vote.

The rewards will be distributed through our own AUR token. The latter will be listed on KyberDMM against USDC (we will incentivise the pool ourselves). AUR tokens are representing other tokens locked in a smart contract, called the “reserve”. LPs receive AUR tokens and have the choice to sell them right now, or wait until the end of the 8 weeks program to unlock the JRT, UMA and KNC held in the reserve contract, by burning AUR. The reserve contract is seeded by Jarvis Network; this is why we would like to receive the KNC token in advance, in order to deposit them in the reserve contract, and to use our UI, built around the concept of the AUR token.

In the case this request will be rejected and the joint LM program will be approved, the AUR token will only hold JRT and UMA, and LPs would earn `KNC and AUR` tokens.
However, mind that using AUR tokens has few interesting consequences:

1. It reduces the selling pressure of the underlying tokens; most likely, LPs with a short term strategy will dump their AUR tokens, without impacting the underlying JRT, UMA and KNC, and LPs who want to keep their tokens will keep their AUR tokens to exchange them at the end of the program for the underlying tokens.
2. It introduces some game mechanics: if the price of the AUR token is below what traders think it will be at the end of the incentive period, they could buy it. If the tokens are oversold, this could constitute a nice opportunity to medium term traders.
3. The admin of the AUR token can add more tokens during the program; for example, the more the TVL of Synthereum grows, the more UMA will be added, which will have a positive impact on the APR.

As part of the campaign launch, there will also be joint marketing efforts with Kyber Network.

Jarvis Network is an ideal candidate for Rainmaker Liquidity Mining on KyberDMM. We expect constant arbitrage opportunities between Jarvis Exchange, which uses Chainlink price feed, and KyberDMM, which will generate trading fees. Jarvis Network’s jFIAT have a direct fiat on and off-ramp on Polygon, to help to buy or sell jFIAT in order to participate in the program.
Jarvis Network will provide liquidity on a new amplified `jEUR-USDC, jGBP-USDC and jCHF-USDC` pool on KyberDMM, as well as amplified liquidity for the `AUR-USDC` pool. Together with requested KNC rewards, total incentives exceed $200,000.

| KNC requested        | Project contribution    | Token pair | Vesting Schedule | Campaign duration |
|---------------------|---------------------------|------------|------------------|-----------------------|
|$140,000(~77,000 KNC Tokens) |$100,000(~6,670 UMA tokens), $200,000(~2,857,000 JRT tokens)|jEUR-USDC, jGBP-USDC, jCHF-USDC and AUR-USDC|conditional based on KNC payment|8 Weeks|

## Ape In

### Project Introduction

Ape In is an NFT-driven project that features a series of mini-games that are designed to offer a consumer-friendly approach to decentralized finance (DeFi). These games function to introduce crypto-centric concepts, such as liquidity farming, to a broader audience while forwarding the industry’s thinking around the utility of NFTs.

The Ape In mini-games all exist within the Ape Island metaverse, a digital world that brings users together to explore exclusive gaming experiences and socialize. Ape Island features the first decentralized, on-chain NFT vaulting system where the main metaverse game unit, the Ape, can be staked to earn the APEIN utility token. This system currently features more than $2.5M in TVL.

The APEIN token has major utility across Ape Island with the primary use case of being the token required for mating Apes to create offspring, which in turn can be vaulted for additional APEIN rewards. APEIN is an inflationary token with substantial deflationary mechanisms, including mating and a built-in burning mechanism on all Ape + item sales.
Ape Island is being developed on Ethereum and Avalanche and APEIN is currently available on both networks.

### Proposal Summary, Motivation, and Key Details

Ape In is proposing a joint liquidity program with Kyber on the Avalanche network.

As part of this program, users will be able to provide liquidity to the upcoming APEIN-WAVAX pair on KyberDMM to receive dedicated LP tokens. These tokens can be staked to earn dual-rewards in both `APEIN and KNC at a 2:1 ratio`.

With the incentivized pool, KyberDMM will become a primary location for APEIN trading on Avalanche. Our team will focus heavy resources and attention on the marketing around this pool, including the creation of unique Kyber-branded Ape NFTs.

The motivation behind this proposal is two-fold:

- To increase our footprint on the low-fee Avalanche network by attracting DeFi-centric users, such as those found within the Kyber community, via APEIN reward distribution. Our goal is to build a dispersed group of APEIN holders who can all participate in the upcoming, exclusive expansion sale of Apes on Avalanche using their farmed rewards.
- To incentivize the lock-up of APEIN to grow the total liquidity available to new users entering our metaverse. Core to our economy is the ability to efficiently acquire APEIN with low-slippage and the KyberDMM is the ideal venue for this pool.
The Ape In team is fully public and has been at the forefront of NFT innovation for the past few years. Our team has been featured in major financial publications, including The Wall Street Journal, Business Insider, Bloomberg, and more.

Ape In will provide $200k worth of APEIN rewards for 8 weeks, in addition to seeding the initial liquidity at a level between `$800k and $1.2M`, depending on market conditions at the time of pool creation. The pair will be `APEIN-WAVAX`.

| KNC requested | Project contribution | Token pair | Vesting Schedule |Campaign duration|
|---------------|----------------------|------------|------------------|-----------------|
| $100,000       |$200,000             |APEIN-WAVAX   |14 Days           |2 Months         |



**`Note`: Minor campaign details (e.g. launch date, vesting schedule) may change if deemed appropriate by both parties. The amount of KNC requested and the partner project's token contribution cannot be changed once the voting campaign is live on kyber.org**