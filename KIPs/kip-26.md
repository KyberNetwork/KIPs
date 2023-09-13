---
kip: 26
title: Configuring the reward distribution system for KNC delegators and delegates
status: Active
type: Updating DAO reward calculation and distribution component
authors: Kyber Network team
created: 2023-09-13
---

```
campaign_type: general
executor: short timelock executor
voting_power: current staked voting power
execution: update reward component; calculate and send voting reward to delegators instead of delegates
start_timestamp: 1694764800 (Friday, September 15, 2023 3:00:00 PM GMT+7)
end_timestamp: 1695369600 (Friday, September 22, 2023 3:00:00 PM GMT+7)
options: 1, 2
option_titles: "Yes", "No"
min_knc_voted_percentage: 40000000000000000 (4%)

```
## Summary

This proposal seeks KyberDAO’s approval to configure the current system of KNC rewards distribution such that delegators (KNC stakers who delegate voting power to another address) are able to directly receive and claim voting rewards proportional to their stake. This way, delegators do not need to trust their delegates to return rewards to them and their delegates can focus solely on governance and voting operations; encouraging more KNC stakers and delegates in the process.

Community discussion around this KIP can be found in the [governance forum](https://gov.kyber.org/t/kip-configuring-the-rewards-distribution-system-for-knc-delegators-and-delegates-discuss/2011). For this KIP to be approved, a minimum quorum of 4% of Total KNC supply is required for the winning option, with a vote differential of 0.01%.

## Motivation

Currently, a KNC staker can vote on KIPs (Kyber Improvement Proposals) to receive KNC rewards that are converted from a portion of KyberSwap trading fees, aligning incentives between KNC holders and KyberSwap adoption.

Alternatively, a KNC staker who lacks the time or ability to regularly engage in governance, can delegate voting power to another address to vote on his or her behalf.

- **Delegator:** KNC staker who delegates voting power to another wallet address, which gains the ability to vote on behalf of the KNC staker.
- **Delegate:** A wallet address that receives voting power from a KNC staker. The delegate only receives voting power to vote; ownership and control of staked KNC remains in the hands of the original KNC staker (the delegator).

In this scenario, rewards are sent to the delegate who votes, and the KNC staker (the delegator) has to trust the delegate to claim and return the rewards owed.

However, this current system introduces two major governance blockers:

- **Operational inconvenience and costs:** After every KIP, the delegate has to vote on behalf of the delegator, claim rewards, calculate rewards owed to their delegator, then spend additional gas costs to return rewards to their delegator.
- **Having to trust delegates for rewards:** There is an element of custodial trust involved as rewards owed to the delegator after a vote are fully controlled by the delegate and there is no guarantee that the delegate would transfer back those rewards. Encouraging delegation within the community is thus not feasible, and naturally the delegation feature sees minimal use.

In order to remove these blockers, we propose that we enable **KNC voting rewards to be directly and transparently distributed (via KyberDAO smart contracts) to delegators, instead of delegates**. Delegates are then able to focus solely on voting on KIPs with their voting power, while delegators can be assured that they will receive the rewards owed.

This convenience would in turn encourage more delegation, more KNC staked to be then delegated, and broader governance participation, since any community member (including projects, key opinion leaders, and ambassadors) can now publish their Ethereum wallet address and ask other users to stake KNC and delegate voting power to them, without users having to worry about not receiving voting rewards.

## Proposed Configuration

Update the current rewards distribution system, such that after each KIP vote, voting rewards get distributed proportionately to:

- KNC stakers who voted on their own
- KNC stakers who delegated voting power to a delegate address who voted on their behalf

For this update, no change is required for the fundamental KyberDAO smart contracts; changes are made only to the voting reward calculation and distribution component.

KNCs stakers who delegate their voting power to a delegate’s address can be assured that they will receive their voting rewards (assuming their delegate votes on the KIPs). 

**Example scenario after the proposed configuration**

- Tom stakes his own 10,000 KNC.
- Tom wants to help other community members by voting on their behalf, so he publishes his voting wallet address; allowing anyone to delegate KNC to him as well.
- Jerry stakes 5,000 KNC and delegates it to Tom. Jerry is the delegator and Tom is Jerry’s delegate.
- Tom can vote on the next KIP with 15,000 KNC voting power. But Tom only receives rewards proportional to his own 10,000 KNC staked.
- Remaining rewards proportional to 5,000 KNC gets distributed to Jerry automatically, not to Tom (as Jerry is the original staker and delegator of that 5,000 KNC).

## Conclusion

As KyberDAO grows in size and complexity, delegation becomes an increasingly important component of governance as it allows for broader and active governance participation, as well as more efficient decision-making.

The current delegation system has operational challenges which presents a high barrier for community adoption of the delegation feature. By simply redirecting rewards to delegators instead of delegates, KyberDAO would make the staking of KNC and the delegation feature a lot more appealing. 

Any community member can publish their wallet address and be a delegate to vote on behalf of others, while being assured that voting rewards will be accurately calculated and distributed.