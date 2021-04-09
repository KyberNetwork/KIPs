---
kip: 7
title: Migrate Kyber DAO to a new architecture
status: Active
type: Migration
authors: Kyber Network team
created: 2021-04-09
---


```
voting_campaign_type: general
voting_start_timestamp: 1618038427
voting_end_timestamp: 1618038430
voting_min_knc_voted_percentage: 40000000000000000
voting_c: 0
voting_t: 0
voting_options: 1, 2
voting_option_titles: "Accept", "Reject"
```

## Summary

Given the major architectural changes and new capabilities introduced by the Kyber 3.0 upgrade and the [KNC token migration](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-6.md), the Kyber team is proposing an upgraded KyberDAO that can better facilitate the governance of this new architecture.

The proposed upgrade consists of a migration that will give the KyberDAO increased governance rights and more flexibility to manage current and future protocols joining Kyber Network, as well as guide KNC’s token behaviour.

## Motivation

With more than 40 weeks and 20 epochs of operation, the KyberDAO has been facilitating decentralized and community-driven decision-making for the benefit of Kyber Network, all KNC holders, and the greater ecosystem.

In the upcoming Kyber 3.0 upgrade, Kyber’s architecture will undergo a significant revamp, transitioning Kyber into a hub of multiple liquidity protocols that cater to a myriad of different use cases in DeFi and beyond. There is a strong emphasis placed on growth and innovation and therefore, the KyberDAO is expected to take an increased governance role to manage and make decisions for all the various protocols that make up the Kyber ecosystem.

While the existing architecture of the KyberDAO caters to current governance requirements, it has several design factors that limit its suitability for its expanded responsibilities in Kyber’s next phase of growth. Therefore, a migration to a more advanced system is required.

## Proposed New KyberDAO System

This KIP aims to further amplify KyberDAO’s role in the long-term governance of Kyber Network, creating a system that efficiently facilitates important decision-making processes with suitable incentives to stimulate growth and innovation.

In the process, changes will be made to how fees are handled and distributed, and the permissions granted to the different KyberDAO stakeholders.

Below are the proposed changes/configurations for the KyberDAO migration:

![DAO architecture](https://raw.githubusercontent.com/KyberNetwork/dao_sc/katana/kyber-gov-architecture.png)

The overall architecture is based off Aave’s governance model with some notable modifications:
1. Enabling the creation and voting of multi-option (generic) proposals
2. voting power will be calculated (initially it will be a strategy that is based on the current KNC staking model)

## KyberDAO Smart Contract Technical Design and Specifications

The design and specification are described in this [audit documentation](https://docs.google.com/document/d/1XjSXI1dWkCJC7PmRzZN_mNhe6YY32pgWPGZRuvefc9U/edit?usp=sharing).

### Configs and Parameters for Deployment

The Kyber team is proposing the following specifications based on:
1. Our review of the KyberDAO voting behaviour from the past 20 epochs 
2. Feedback from our delegates / 3rd-party staking pools / KyberDAO partners
3. Referencing the governance system and processes from other projects such as Aave
4. The our current staking statistics vs the total KNC supply in the market
5. The need to have governance safeguards to ensure that any decision or contract alteration will always be preceded by a suitable time period of preparation and reflection, as well as a minimum voter participation threshold

|            | Actors           | Permissions                                                            | Proposed Contract       |
|------------|------------------|------------------------------------------------------------------------|-------------------------|
| KNC Token  | Miner            | Mint KNC                                                               | Long Timelock Executor  |
|            | Proxy Admin      | Change KNC implementation                                              | Long Timelock Executor  |
|            | Withdrawal Admin | Withdraw tokens from the contract due to accidental transfer of tokens | ⅔ Multisig              |
| Governance | Admin            | Authorize and deauthorize executors and strategies                     | Long Timelock Executor  |
|            | Executor Admin   | Queue, cancel, and execute proposal transactions                       | The governance contract |
|            | DAO Operator     | Create and cancel proposals                                            | ⅗ Multisig              |

### Timelock Executor Configurations

| Properties          | Definition                                                                                                                   | Short Timelock | Long Timelock |
|---------------------|------------------------------------------------------------------------------------------------------------------------------|----------------|---------------|
| Delay               | Waiting time to execute proposals                                                                                            | 12 hours       | 1 week        |
| Grace period        | Proposal execution period before it expires                                                                                  | 4 days         | 7 days        |
| Min delay           | Minimum time in the range of a delay config                                                                                  | 1 hour         | 24 hours      |
| Max delay           | Maximum time in the range of a delay config                                                                                  | 24 hours       | 2 weeks       |
| Min vote duration   | Minimum voting duration of a proposal                                                                                        | 4 days         | 7 days        |
| Max voting options  | Maximum number of options in a proposal                                                                                      | 8              | 8             |
| Vote differential   | The difference needed between the votes behind the For/Against options (percentage of Total KNC supply in the market needed) | 0.01%          | 4%            |
| Min quorum          | Minimum percentage of Total KNC supply in the market needed for the winning option                                           | 4%             | 15%           |

### Changes to the BRR Framework

KyberDAO is currently using the [Burn/Reward/Rebate framework (BRR)](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-2.md) to decide on the % of network fees that are allocated to burning KNC, rewarding DAO voters, or rebates for professional market makers. BRR worked well as a general framework used for aligning stakeholder incentives while Kyber is in its current iteration as a single liquidity protocol.

However, with Kyber 3.0, Kyber will become a hub of liquidity protocols each with different use cases. It will be possible for each protocol (e.g. DMM Protocol and Professional Liquidity Protocol for market makers) to have its own set of fees and requirements.

Post-migration, the KyberDAO will establish an entirely different framework for collecting fees from individual protocols in the Kyber liquidity hub. The final network fee campaign that uses the BRR framework will be [BRR-20](https://kyber.org/proposal/25).

BRR-20 results will be used for the network fee allocation until the new framework is implemented.

## Important Considerations

1. It is important to note that it is possible for the current governance mechanisms and permissions proposed for the new KyberDAO to be changed in the future, or new suitable strategies and mechanisms from the community to be added, subject to a proposal and vote by the new KyberDAO itself.
2. The Kyber core team is the current network maintainer and one of the main actors/admin in the KyberDAO, helping to execute critical tasks to maintain and grow the network. But the team alone does not have the power to implement major changes to the KyberDAO and the protocols in the network. Any contract alteration must be first decided by a KyberDAO vote.

## Conclusion

Kyber is on a path of progressive decentralization. KIP-7 will help create a more robust KyberDAO system that allows Kyber stakeholders, including token holders, traders, token teams, and developers, to have greater participation in Kyber’s governance and contribute to its development. As usual, all important decisions pertaining to the KyberDAO, will be decided as one Kyber community in a transparent manner, and the community is encouraged to actively discuss this KIP in the [governance forum](https://gov.kyber.org/).

