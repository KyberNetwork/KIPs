---
kip: 29
title: Add DAO multisig to the smart contract strategy for converting & receiving LP fees
status: Active
type: Updating smart contract strategy
authors: Kyber Network team
created: 2023-12-11
---

```
campaign_type: binary
executor: long timelock executor
voting_power: current staked voting power
execution: Add DAO multisig to the smart contract strategy for converting & receiving LP fees
start_timestamp: 1702364400 (Tuesday, December 12, 2023 2:00:00 PM GMT+7)
end_timestamp: 1702969200 (Tuesday, December 19, 2023 2:00:00 PM GMT+7)
options: 1, 2
option_titles: "Yes", "No"
min_knc_voted_percentage: 200000000000000000 (20%)

```
## Summary

To further optimize KyberSwap and KyberDAO operations, the team proposes to include the DAO multisig wallet (on every chain) in the current smart contract strategy that manages the reception of KyberSwap LP (liquidity provider) fees, followed by making the DAO multisig the new receiving address for Classic protocol LP token fees.

These steps are necessary to optimize the Classic LP token fee collection and transfer the remaining Classic protocol (old KyberDMM) LP fees (currently worth ~$30K USD) out of the [Treasury pool](https://debank.com/profile/0x0e590bb5f02a0c38888bffb45dee050b8fb60bda) to the DAO multisig wallet. **These fees, which were collected for eligible KNC voters, can then be converted to KNC to be distributed to these eligible KNC voters.** 

KyberDAO would vote Yes/No on whether to proceed with these important changes. For this long executor-based KIP to be approved, a minimum quorum of 20% of Total KNC supply is required for the winning option, with a vote differential of 15%.

This KIP was raised in the governance forum [here](https://gov.kyber.org/t/kip-29-draft-add-dao-multisig-to-the-smart-contract-strategy-for-converting-receiving-lp-fees-discuss/2213).

## Motivation

Previously, in our old, legacy KyberDMM system, KyberDMM LP fees were stored in the Treasury pool: [0x0e590bb5f02a0c38888bffb45dee050b8fb60bda](https://debank.com/profile/0x0e590bb5f02a0c38888bffb45dee050b8fb60bda) on Ethereum. 

For liquidation to KNC (converting LP fees to KNC), an old network system (an outdated smart contract) was used, 0x9AAb3f75489902f3a48495025729a0AF77d4b11e, which was protected by the Chainlink oracle.

However, this old network system is now outdated and many new tokens are not supported by that Chainlink oracle. As such, we are unable to use this old network system to execute on-chain liquidation to convert the remaining KyberDMM LP fees to KNC and distribute the rewards that belong to KNC voters.

To resolve this issue, we would have to pull the KyberDMM LP fees out of the Treasury pool and send the fees to the DAO multisig wallet: 0x91c9d4373b077ef8082f468c7c97f2c499e36f5b

To do that, we need to add the DAO multisig (on every chain) to the current smart contract ‘strategy’; i.e. the smart contract used to receive LP fees.

In addition, we need to change the address to receive Classic (old KyberDMM) LP token fees to the DAO multisig instead of the Treasury pool, and subsequently conduct manual liquidation of fees to KNC, before distributing it to voters. 

## Proposed Changes

1. Add DAO multisig (on every chain): 0x91c9d4373b077ef8082f468c7c97f2c499e36f5b to the current smart contract strategy i.e. the smart contract to receive LP fees.
2. Transfer KyberDMM LP fees (on every chain)
   - From Treasury pool: 0x0e590bb5f02a0c38888bffb45dee050b8fb60bda
   - To DAO multisig: 0x91c9d4373b077ef8082f468c7c97f2c499e36f5b
   - *Note: KyberDMM LP fees remaining = ~$30K USD*
4. Change the receiving address for Classic LP token fees
   - From Treasury pool: 0x0e590bb5f02a0c38888bffb45dee050b8fb60bda
   - To DAO multisig: 0x91c9d4373b077ef8082f468c7c97f2c499e36f5b

Once all the above steps have been completed, the old network system will not be used moving forward.

## Conclusion

Without taking the aforementioned steps, eligible KNC voters would not be able to gain access to the ~$30K USD worth of funds currently residing in the old Treasury pool. As such, the team is proposing that KyberDAO approves the required changes as soon as possible to help eligible KNC voters obtain the rewards they deserve and optimize fee operations to accelerate future development.

*Note: This KIP is unrelated to the Elastic protocol security topic.*
