---
kip: 19
title: Calibrating KyberDAO Governance Parameters
status: Active
type: Updating DAO Configuration
authors: Kyber Network team
created: 2022-05-06 test
---

```
campaign_type: binary
executor: long timelock executor
voting_power: current staked voting power
execution: Calibrate KyberDAO Governance Parameters
start_timestamp: 1650351600 (Tuesday, 19 April 2022 07:00:00 UTC)
end_timestamp: 1650956400 (Tuesday, 26 April 2022 07:00:00 UTC)
options: 1, 2
option_titles: "Accept", "Reject"
min_knc_voted_percentage: 150000000000000000 (15%)

```

## Summary

KyberDAO’s governance parameters have worked well thus far, with comprehensive governance safeguards that ensured no one, including the Kyber team, can implement major changes to the DAO and the protocols in the network without going through a DAO vote in a decentralized manner.

However, with the fast-changing DeFi landscape, further safeguards are required. We would like to take the pre-emptive step of proposing certain calibrations to ensure that Kyber continues to have a decentralized governance process that is protected against malicious attacks. This has also been suggested by members of the community and DeFi ecosystem.

The main changes we are proposing are:

1. Higher Voting Quorum

2. Higher Vote Differential

3. Changes to Kyber Ecosystem Delegates

### Proposed Changes

1. Higher Voting Quorum

Current Voting Quorum; minimum percentage of Total KNC supply used to vote in order for the vote to pass: Short timelock: 4%. Long timelock: 15%.

- We propose an increase in the long timelock voting quorum to 20%.

This means at least 20% of the total KNC supply would need to vote, in order for the winning option to be executed. This helps prevent vote centralization.
Note: We have short timelock and long timelock execution parameters based on the nature and criticality of the vote. Short timelock is used for smaller changes that require faster execution. For example, allocating KNC from the ecosystem fund for a joint liquidity mining campaign with a DeFi project. On the other hand, long timelock is used for more critical changes to the DAO or system. For example, it helps control the admin/minter of the KNC and governance contracts.

2. Higher Vote Differential

Current Vote Differential; difference needed between the votes behind the For/Against options (percentage of Total KNC supply in the market needed): Short timelock: 0.01%. Long timelock: 4%.

- We would like to increase the long timelock vote differential to 15%.

This means the number of token holders that voted in favor of the winning option needs to be at least 15% of the total KNC supply more than those who voted against, in order for the winning option to be executed. Again, this helps prevent vote centralization and allows a substantial margin between ‘for’ and ‘against’ votes.

3. Changes to Kyber Ecosystem Delegates

The Kyber team had previously delegated a portion of our own KNC tokens and voting power to top projects that have contributed to Kyber’s ecosystem development over the years. These were ecosystem delegates that participated in discussions about Kyber’s development and voted on proposals using their delegated KNC.

The previous 9 ecosystem delegates were:
DeFi Saver, Enjin, Fulcrum (bZx), InstaDApp, Trust, OneBit Quant, FPR Representative, Kyber Community Pool, Unagii by StakeWithUs.

To encourage greater diversity and accommodate new projects in the ecosystem, we would like to refresh the lineup and delegate more KNC to ecosystem projects (up to 50% of Kyber team’s tokens). We will propose an updated list of ecosystem delegates later, with some changes.
Ecosystem delegates comprising of DeFi and GameFi projects ensure that some level of KNC voting power will always lie in the hands of important stakeholders who are central to Kyber’s development and long-term goals, while giving them a sense of ownership over the value they contribute to the protocol.

### New KyberDAO Configurations

#### DAO Operator

There is a 5/9 multisig with the role of a DAO operator that assists with operational tasks and ensuring the integrity of the DAO. They are a mix of Kyber team members and founders of external DeFi projects with no direct affiliation to Kyber.

daoOperator address (multisig): 0xe6a7338cba0a1070adfb22c07115299605454713

1. Loi - Kyber (representing the Kyber founding team) 0xc8a1dab586dee8a30cb88c87b8a3614e0a391fc5

2. Victor - Kyber (representing developers)  
   0x8180a5ca4e3b94045e05a9313777955f7518d757

3. Mike - Kyber (representing the smart contracts team) 0xBE2F0354D970265BFc36D383af77F72736b81B54

4. Sunny - Krystal (representing DeFi Dapps) 0xdE6BBD964b9D0148d46FE6e2E9Cf72B020ADc519

5. John - Signum Capital (representing VCs and KNC holders) 0x8eC1455f17d9E021Acc8a30F23461DEdff5018Ba

6. Hunter/DeFi Dude - (representing the DeFi Community) 0x499b2408A0a6B43fea49Df79d98246f88ECC8465

7. 0x7a33 - Anonymous (representing professional market makers) 0xffF96a443aB8e8eFF4621c1Aa02Bbd90aD39DA57

8. Michael - xToken (representing staking pools/Dapps) 0x2171861D0943b50d375a800E6c6ea061758C8eB4

9. Michael - Unagii (representing staking pools/Dapps) 0x6c7C332a090c8D2085857cf3220eA01C6d45a723

#### New Configurations

| Subject    |      Actors      |                                                            Permissions | Proposed Contract      |
| ---------- | :--------------: | ---------------------------------------------------------------------: | ---------------------- |
| KNC Token  |      Miner       |                                                               Mint KNC | Long Timelock Executor |
|            |   Proxy Admin    |                                              Change KNC implementation | Long Timelock Executor |
|            | Withdrawal Admin | Withdraw tokens from the contract due to accidental transfer of tokens | 3/5 Multisig           |
| Governance |      Admin       |                     Authorize and deauthorize executors and strategies | Long Timelock Executor |
|            |  Executor Admin  |                       Queue, cancel, and execute proposal transactions | Governance Contract    |
|            |   DAO Operator   |                                            Create and cancel proposals | 5/9 Multisig           |

#### Timelock Executor Configurations

| Properties         |                                                          Definition                                                          | Short Timelock | Long Timelock |
| ------------------ | :--------------------------------------------------------------------------------------------------------------------------: | -------------: | ------------- |
| Delay              |                                              Waiting time to execute proposals                                               |       12 hours | 1 week        |
| Grace period       |                                         Proposal execution period before it expires                                          |         4 days | 7 days        |
| Min delay          |                                         Minimum time in the range of a delay config                                          |         1 hour | 24 hours      |
| Max delay          |                                         Maximum time in the range of a delay config                                          |       24 hours | 2 weeks       |
| Min vote duration  |                                            Minimum voting duration of a proposal                                             |         4 days | 7 days        |
| Max voting options |                                           Maximum number of options in a proposal                                            |              8 | 8             |
| Vote differential  | The difference needed between the votes behind the For/Against options (percentage of Total KNC supply in the market needed) |          0.01% | 15%           |
| Min quorum         |                      Minimum percentage of Total KNC supply in the market needed for the winning option                      |             4% | 20%           |

The new Timelock Executor has been deployed here: 0x7d4d05B1a1E5775a9C6ca248ABBE629B52C1D9D9 with corresponding configurations.

### Other Important Considerations

1. It is possible for the current governance mechanisms and permissions proposed for the new KyberDAO to be changed in the future, or new suitable strategies and mechanisms from the community to be added, subject to a proposal and vote by the new KyberDAO itself.

2. The Kyber core team is the current network maintainer and one of the main actors/admin in the KyberDAO, helping to execute critical tasks to maintain and grow the network. But the team alone does not have the power to implement major changes to the KyberDAO and the protocols in the network. Any contract alteration must be first decided by a KyberDAO vote.

## Conclusion

Kyber is on a path of progressive decentralization. Although our current governance framework is largely based on Aave (considered best practice), we are always open to community feedback and will optimize it when deemed suitable. This KIP will help KyberDAO ensure greater decentralization and diversity, while strengthening its ability to withstand attacks on its governance process by malicious actors.