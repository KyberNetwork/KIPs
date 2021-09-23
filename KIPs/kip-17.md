---
kip: 17
title: Joint LM with Unbound Finance, EvryNet and DeFi Yield Protocol
status: Active
type: Spend KNC
authors: Kyber Network team
created: 2021-09-22
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: use KNC from 0x91c9D4373B077eF8082F468C7c97f2c499e36F5b (KyberDAO multisig to handle KNC bridging between ethereum and other chains) to run Joint Liquidity Mining programs depends on voting result.
start_timestamp: 1632391200 (Thur, 23 Sep 2021 10:00:00 UTC)
end_timestamp: 1632812820 (Tue, 28 Sep 2021 07:07:00 UTC)
options: 1, 2, 3, 4
option_titles: "Unbound", "EvryNet", "DeFi Yield", "None"
min_knc_voted_percentage: 30000000000000000

```

## Summary

Based on forum discussions, the Kyber community is proposing that the following projects be included in the `Rainmaker` Joint Liquidity Mining program:

1. Unbound Finance on Ethereum, for [UND-USDT,UND-KNC and UND-UNB](https://gov.kyber.org/t/joint-liquidity-mining-on-ethereum-with-unbound-finance-on-kyber-dmm/486).

2. EvryNet on Ethereum, for [EVRY-ETH and EVRY-USDT](https://gov.kyber.org/t/evrynet-evry-joint-liquidity-mining-on-kyber-dmm/481).

3. DeFi Yield Protocol (DYP) on Avalanche, for [DYP-WAVAX](https://gov.kyber.org/t/joint-liquidity-mining-on-avalanche-with-defi-yield-protocol-dyp-on-kyberdmm/452).


## Unbound Finance

### Project Introduction

Unbound Finance is a Cross-Chain Aggregator Layer For AMMs

Unbound finance is a decentralized, cross-chain liquidity protocol that is building the next money lego by unlocking the liquidity from AMMs. The protocol is the ‘First-Ever-Debt-Free Liquidity Provision System’ that collateralizes LP Tokens to generate synthetic assets including UND and uETH. The protocol charges no interest rates and is liquidation-free.

### Proposal Summary, Motivation, and Key Details

Unbound Finance is proposing that UND pools be included in the Rainmaker Liquidity Mining program to help improve liquidity for selected UND token pairs on the KyberDMM protocol. This is applicable to Ethereum and Polygon networks.

Users can mint UND stablecoin by staking LP tokens of select pools from DEXs such as Uniswap or KyberDMM on the Unbound platform.

With their new UND tokens, users would need a venue to trade or add liquidity for UND tokens. KyberDMM will be the first venue to access UND liquidity, which would bring plenty of volume and fees to the protocol.

During the campaign period, liquidity providers who add liquidity (deposit tokens) on the eligible UND pools on KyberDMM will receive LP tokens that can be staked on the Yield page for additional KNC token rewards.

**Value-added process:**

KyberDMM liquidity providers can visit Unbound’s platform and deposit their LP tokens to Unbound’s ‘liquidity lock contract’, which mints UND while immediately depositing the LP tokens to KyberDMM’s farming contracts for KNC rewards.

As part of the campaign launch, there will also be joint marketing efforts with Kyber Network.

**Process outline:**

1. AMM LP tokens of all DEXs gets deposited first on the Unbound platform.

2. Users mint the UND stablecoin. (For stable coin LP tokens, the loan to value is as high as 80%)

3. Users take UND and visit Kyber to add liquidity to UND/USDT, UND/KNC and UND/UNB pools.

4. Kyber DMM LP tokens (USDT/USDC, UND/USDT, UND/KNC, UND/UNB) will be whitelisted on Unbound. Users can lock up these LP tokens on Unbound again and mint more UND and take them back to Kyber.

5. Every time a user locks LP tokens in Unbound’s systems, the user can choose the farming pool where they want to farm the tokens. For every user, per farming pool a new smart contract wallet is deployed from Factory (called a yield wallet). Since the LP tokens are deployed to the farming contract from a user-specific contract wallet, he can claim accumulated rewards from the contract directly. So the user will continue getting the USDT/USDC rewards on Kyber DMM even when they lock up those LP Tokens on Unbound since those LP tokens will be parked back on KyberDMM. Basically, for users, rewards get doubled.

**Example:**

- Rewards from the USDT/USDC pools on KyberDMM.

- Lock up USDT/USDC LPTs on Unbound to mint UND of 80% value of their LPT.

- Add liquidity to UND /USDT, UND/KNC and UND/UNB pools to get more rewards.

**Key reasons why Unbound is an ideal candidate for Rainmaker Liquidity Mining:**

Unbound Finance as a DeFi project has a lot of support, with 15k+ followers on Twitter and 5500+ Telegram members. It’s also backed by well-known funds in the space such as Pantera, Arrington Capital, CMS,Ledgerprime, Hashed, Hashkey and many more. It has some industry veterans on board as investors as well.

Unbound understands the powerful benefits KyberDMM provides e.g. high capital efficiency and is keen to have KyberDMM as the first venue for UND liquidity during its launch phase. Coupled with KNC liquidity mining incentives, this would bring plenty of volume and fees to KyberDMM. Similar to Kyber, Unbound is venturing into different chains and will continue to channel liquidity into KyberDMM.

Unbound Finance is targeting approximately $15 M+ in liquidity to be deposited across the participating UND pools (AMP=200).

- UND/KNC
- UND/USDT
- UND/UNB

In the near future, Unbound will also look at creating and incentivising liquidity pools for the UNB governance token on KyberDMM after the token sale has been completed.

In return, Unbound Finance would like to request $500k in KNC incentives for a 4 month liquidity mining campaign on Ethereum chain Kyber DMM split between:

- UND/KNC
- UND/USDT
- UND/UNB

| KNC requested | Project contribution | Token pair | Vesting Schedule |Campaign duration|
|---------------|----------------------|------------|------------------|-----------------|
| $250,000       |Refer to note             |UND-USDT,UND-KNC and UND-UNB   |30 Days           |8 Months         |

* `Note:` 60% of the minting fee that Unbound will generate will be given as rewards to
UND/KNC, UND/USDT and UND/UNB pools.

Along with this, once $UNB goes live, we will also give $500k in rewards to UND/KNC, UND/UNB and UND/USDT pools on Kyber DMM. Unbound Finance will thus give more rewards Kyber (Matching KNC rewards 1:1 plus UND minting fee goes to KNC Pools). `Unbound governance token is not live yet.`

### Terms and Conditions

**Liquidity Mining**

`Part A:` 2 -months LM campaign with a 125K KNC(~$250K) and 60% of UND minting fee reward for 3 UND pools. Target min. TVL $15M.

- UND/USDT
- UND/KNC
- UND/UNB

`Part B (conditional; depends on Part A):` If Unbound hits the target TVL of $15M, KyberDMM will unlock the remaining 125K KNC for the 3rd and 4th month.

If Part A doesn’t hit the target TVL of $15M, the campaign ends temporarily after 2 months.

`Part C:` If part A conditions are not met, $250k in UNB rewards will be given to the 3 pools mentioned above for 2 months after completion of month 2 (Part A).
Total LM Campaign = 2+2 months.

If part A conditions are met, $500k in UNB rewards will be given to the 3 pools mentioned above for 4 months after completion of 4 months (Part B).

Total LM Campaign = 4+4 months.

**Exclusivity:**

For the first month, KyberDMM will be the only official LM partner on Ethereum.

**Promotions:**

1 main CTA button on the Unbound app/site for adding UND liquidity for Ethereum chain with links to KyberDMM.
Marketing communications on Unbound social channels to direct UND LPs to farm on KyberDMM.


## EvryNet(EVRY)

### Project Introduction

EvryNet is a blockchain protocol focused on developing an inclusive, open-source platform to provide financial services and products catering for the unbanked/underbanked.

### Proposal Summary, Motivation and Key Details

EvryNet is proposing a joint liquidity mining program with Kyber to help improve liquidity for the EVRY token on KyberDMM protocol.

During the campaign period, liquidity providers who add liquidity (deposit tokens) on the eligible `EVRY-ETH and EVRY-USDT` pools will receive LP tokens that can be staked on the Yield page for additional EVRY and KNC token rewards. As part of the campaign launch, there will also be joint marketing efforts with Kyber Network.

EvryNet is an ideal candidate for Rainmaker Liquidity Mining on KyberDMM. The EvryNet project was jointly developed with Kyber Network and Stellar. EvryNet is also backed by industry leading names in Southeast Asia such as CP Group (TH), Hanwha Group (KR), 7Bank (JP), Unipresident (TW), UOB, Wanshiang/Hashkey, Signum Capital and Lightnet Group.

EvryNet’s first dAPP, Evry.Finance, is a multi-chain DEX that focuses on bringing institutional investors into DeFi has been gaining momentum. Evry.Finance will include institutional specific features such as a multi-sig wallet, enterprise smart contracts, compliance reports, combination of orderbook and AMM/DMM as well as other financial products to facilitate institutional investors’ participation in DeFi. Both EvryNet and Evry.Finance are in testnet and are being audited by three reputable names in the crypto cybersecurity space before being released to the public.

EVRY will provide the minimum requirement of $200,000 worth of liquidity on KyberDMM. Together with requested KNC rewards, total incentives equal $280,000; with the understanding that should the pool perform well, more KNC and EVRY rewards can be allocated at a closer ratio of KNC:EVRY in a new DAO proposal.

| KNC requested        | Project contribution    | Token pair | Vesting Schedule | Campaign duration |
|---------------------|---------------------------|------------|------------------|-----------------------|
|$80,000 |$200,000 |EVRY-ETH and EVRY-USDT|14 Days|3 Months|


## DeFi Yield Protocol(DYP)

### Project Introduction

The DeFi Yield Protocol (DYP) is a unique platform that offers solutions for yield farming, staking, NFTs, and enabling users to leverage the advanced trading tools of the DYP. What makes the DYP a unique yield farming aggregator? The DYP made history in the DeFi space by becoming the first and only protocol to reward users in Ethereum.
The protocol employs an anti-manipulation feature that aims to limit the market impact on users’ converting rewards into ETH and other native platform tokens. Anti-manipulation aims to maintain stability, fair access to liquidity, and provide a secure and simplified DeFi platform for users of all sizes.
The core feature of the DYP is the decentralized tool dashboard. It provides advanced features, such as Decentralized Score, Unique Community Trust Vote System, DYP Locker, Yield Farm Data, and LaunchPad, allowing investors to make informed decisions that maximize yields and reduce risks.
**DeFi Yield Protocol is a multi-chain platform available on Ethereum, Binance Smart Chain, and Avalanche. Since launch our users have earned 8791 ETH, 7195 BNB, and 11438 AVAX worth $34,648,092.**
What is the use case of DYP token? DYP serves as the fuel for all products in the DeFi Yield Protocol ecosystem and it could be used in the following use cases:

- Transaction fees for NFTs smart contract operations
- Staking on Ethereum Network
- Yield Farming on Ethereum, Binance Smart Chain, and Avalanche
- Part of the DYP Earn Vault Strategies
- Community voting for decentralized Governance
- DYP Referral System
- Subscription tokens for DYP Tools Premium
- DYP Locker fulfil security for smart contracts by locking their liquidity; DYP is the token used for the liquidity lock
- DYP Launchpad v1.0 will offer multiple tiers based on amount of locked DYP

This is just scratching the surface, though. Ultimately, DYP is a requirement for entering the DeFi Yield Protocol ecosystem and unlocking an unprecedented level of security for projects and individual asset holders.

### Proposal Summary, Motivation, and Key Details

DeFi Yield Protocol is proposing a joint liquidity program with Kyber on the Avalanche network.

As part of this program, users will be able to provide liquidity to the upcoming DYP-WAVAX pair on KyberDMM to receive dedicated LP tokens. These tokens can be staked to earn dual rewards in both DYP and KNC at a 2:1 ratio.

With the incentivized pool, KyberDMM will become a primary location for DYP trading on Avalanche. Another important aspect of the collaboration will be the integration of DYP Tools with KyberDMM for Ethereum, Binance Smart Chain, and Avalanche networks.

**Motivation:**

DeFi Yield Protocol has been already integrated with Avalanche and launched a couple of products including yield farming with AVAX rewards, buyback program, bridge, and DYP Tools. The integration with Avalanche also includes DYP NFTs and LaunchPad, these products are expected to be launched in the next 30 days. **Since the launch of the DYP Farming on Avalanche that happened two months ago, we have paid to the farmers 11438 AVAX worth $830,170. Also, in just one-month DYP worth $370,425.35 has been bought using the Buyback program on Avalanche.**
DYP Tools launch on Avalanche took place just two weeks ago and we have at least 1000 unique users each week from Avalanche network.

With this program we will attract more DeFi users found within the Kyber community, with DYP-KNC reward distribution. Our goal is to expand both Kyber and DeFi Yield Protocol ecosystems.

DeFi Yield Protocol will provide $200k worth of DYP rewards for 8 weeks, in addition to seeding the initial liquidity at a level between $400k and $600k, depending on market conditions at the time of pool creation. The pair will be DYP-WAVAX.

| KNC requested | Project contribution | Token pair | Vesting Schedule |Campaign duration|
|---------------|----------------------|------------|------------------|-----------------|
| $100,000       |$200,000             |DYP-WAVAX   |No vesting           |2 Months         |


**`Note`: Minor campaign details (e.g. launch date, vesting schedule) may change if deemed appropriate by both parties. The amount of KNC requested and the partner project's token contribution cannot be changed once the voting campaign is live on kyber.org**