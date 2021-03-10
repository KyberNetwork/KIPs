---
kip: 6
title: Migrate KNC token to a new implementation
status: Active
type: Migration
authors: Kyber Network team
created: 2021-03-10
---


```
voting_campaign_type: general
voting_start_timestamp: 1615532827
voting_end_timestamp: 1616396827
voting_min_knc_voted_percentage: 40000000000000000
voting_c: 0
voting_t: 0
voting_options: 1, 2
voting_option_titles: "Accept", "Reject"
```

## Summary

The Kyber team is proposing a KNC migration to make the Kyber Network Crystal (KNC) token more dynamic and flexible with the capacity to undergo upgrades more efficiently. This new KNC token contract gives greater control to the KyberDAO, enabling it to upgrade the token and mint or burn tokens as necessary to better support innovation and growth, bootstrap liquidity, and enable Kyber to adapt quickly within the fast-changing DeFi landscape.

## Motivation

We intend to greatly strengthen the KNC token’s role as a governance and incentive mechanism to allow the KyberDAO to further drive growth and value creation for Kyber Network. 

The current KNC token contract has several design factors that make it unsuitable to meet the fast-changing needs of Kyber’s next phase of growth:
1.  The token is non-upgradable meaning any major improvements and functionality changes require the an inconvenient full smart contract migration
2.  The KyberDAO has no steering mechanism for the token’s behaviour
3.  Token supply is fixed, and therefore the KyberDAO is not able to support new initiatives or user growth through funding when when the opportunity arises

Kyber 3.0 will transition Kyber into a hub of multiple liquidity protocols that cater to different DeFi use cases coupled with a strong emphasis on growth and innovation. As such, a highly flexible KNC token contract design, amplified governance powers, and a dynamic supply with a clear incentive system is required to keep pace with prevailing and upcoming DeFi trends.

## Proposed KNC Contract Design

We are proposing a migration to a new KNC contract that will allow the KyberDAO and KNC token to be more dynamic and flexible to adapt to DeFi trends and support growth initiatives.

If the migration is approved, the new version of KNC will have a new token contract and address but will retain its ticker and logo. The old token contract's ticker and symbol will be changed to prevent any confusion. 

### Token Upgradability

We propose that the new token contract be deployed as a proxy that permits a wide range of upgrading capabilities, including adding new functions to the token if required. This will allow the KyberDAO to upgrade core functionalities in the contract without interrupting the ongoing usage of KNC by traders, exchanges, dapps and other stakeholders.

### Dynamic Token Supply

We propose that KNC be upgraded into a token with a DAO-controlled dynamic supply to better support different types of DeFi innovation. KyberDAO will have the important ability to generate new KNC tokens if necessary to fund new protocol development, bootstrap adoption on protocols (e.g. liquidity mining on the DMM), and achieve network effects in order to accelerate growth and innovation. These initiatives will help bring more users into the Kyber ecosystem. The KyberDAO will be responsible for governing and facilitating this entire process in a transparent and community-driven manner, with safeguards implemented to prevent abuse.

## Important Considerations

1. Based on extensive forum discussions with the Kyber and DeFi community, we have established certain key considerations regarding the KNC migration.
2. There have been concerns raised about the possibility of KNC inflation post-migration, where any new KNC minted as incentives for specific beneficiaries will dilute the stake and voting power of the rest of the KNC holders. Another concern is the abuse of KNC’s flexibility to mint exorbitant amounts for the needs of select parties at the expense of the majority of KNC holders.
3. Given the aforementioned concerns, **stringent safeguards and technical/governance mechanisms** will be introduced post-migration to ensure that any token contract alteration will always require a high participation threshold and consensus by KNC holders.
4. Examples of governance mechanisms that will allow us to configure the criterion include logr timelocks before the effects take place, minimum voting quorum and a vote differential (% difference between ‘For’ and ‘Against’ voting results). For instance, AAVE, which has similar token upgradability features has a timelock period of 2 weeks, and requires at least 20% of the AAVE supply voting yes with a vote differential of 15%.
5. Methods were also proposed to ensure an optimal KNC circulating supply in the market, even in a scenario where there is minting of additional KNC tokens. Examples include making it mandatory for all KNC rewards distribution to have a partial lock-up system by being milestone-based or following a suitable vesting schedule.
6. All these ideas are not finalized and need to be discussed in subsequent KyberDAO proposals. The team is committed towards transparency and the implementation of critical safeguards to ensure the integrity of the KNC token model.

## Conclusion

The proposed migration will greatly strengthen the KNC token’s critical role as a conduit for Kyber governance, innovation, and value creation. All important decisions pertaining to KNC smart contract upgrades, new token generation/burning, new protocols, and growth initiatives, will be decided as one Kyber community in a transparent manner. As a community, a key objective for us is to ensure that KNC continues to play a valuable and central role in the Kyber and DeFi ecosystem.

