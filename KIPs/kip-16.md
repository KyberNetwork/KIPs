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
end_timestamp: 1631948827 (Sat, 18 Sep 2021 07:07:07 UTC)
options: 1, 2, 3
option_titles: "DeFi Warrior", "Jarvis", "None"
min_knc_voted_percentage: 30000000000000000

```

## Summary

Based on forum discussions, the Kyber community is proposing that the following projects be included in the `Rainmaker` Joint Liquidity Mining program:

1. DeFi Warrior(FIWA) on BSC, for [FIWA-USDT](https://gov.kyber.org/t/joint-liquidity-mining-defiwarrior-fiwa-token-on-kyberdmm/421)

2. Jarvis Network on Polygon, for [jEUR-USDC, jGBP-USDC, jCHF-USDC and AUR-USDC](https://gov.kyber.org/t/joint-lm-with-jarvis-network-for-incentivizing-forex-pools/372/18).


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
- There are over 200,000 members in the DefiWarrior community and many are liquidity providers. DefiWarrior has integrated KyberDMM hence many DefiWarrior users are also indirect KyberDMM users. 

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
Jarvis Network will provide liquidity on a new amplified `jEUR-USDC, jGBP-USDC and jCHF-USDC` pool on KyberDMM, as well as amplified liquidity for the `AUR-USDC` pool. Together with requested KNC rewards, total incentives exceed $200,000. Note that `AUR` token is yet to be deployed.

| KNC requested        | Project contribution    | Token pair | Vesting Schedule | Campaign duration |
|---------------------|---------------------------|------------|------------------|-----------------------|
|$140,000(~77,000 KNC Tokens) |$100,000(~6,670 UMA tokens), $200,000(~2,857,000 JRT tokens)|jEUR-USDC, jGBP-USDC, jCHF-USDC and AUR-USDC|conditional based on KNC payment|8 Weeks|


**`Note`: Minor campaign details (e.g. launch date, vesting schedule) may change if deemed appropriate by both parties. The amount of KNC requested and the partner project's token contribution cannot be changed once the voting campaign is live on kyber.org**