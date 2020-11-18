---
kip: 5
title: Framework for the KLP Process
status: Active
type: Information
author: Kyber Network team
created: 2020-11-18
---

## Summary:

A KLP (Kyber Listing Proposal) will be submitted for every new ERC-20 token or reserve that has to be added to the network. The KLP process will provide a clear agenda for stakeholders to approve new tokens and reserves through the KyberDAO (Kyber.org), allowing a constant polling of the community and dynamic governance of the token and reserve listing process.

## Motivation:

* To progressively give more control of Kyber Network to the KyberDAO, starting by having the KyberDAO approve new token and reserve listings.
* Gradually involve the community more in complex decision-making e.g. considering new reserve types.
* KLP is part of Kyber’s commitment towards transparency and community engagement while on the path of progressive decentralization.

## KLP Framework:

As the KyberDAO maintainer, the Kyber team has proposed this starting framework for the KLP.
1. **1st approval phase:**
   * The Kyber team receives a new ERC-20 token or reserve listing request. KLP Pull Request with the necessary information will be submitted to Github.
   * Requests can come from community members or token teams. The Kyber team will decide whether to include these requests or not.

2. **2nd approval phase:** 
   * The KyberDAO multisig will approve the KLP for a new voting campaign on Kyber.org 
   * One KLP voting campaign can cater to multiple tokens and/or reserves. KyberDAO will vote on a basket of tokens/reserves to be listed.
   * There will be 2 voting options for each KLP campaign, Accept or Reject.
   * Once a new token is approved, any existing reserve on the network can list that token and provide liquidity for it.

3. **Rejected KLPs**
   * If a KLP is rejected, the KyberDAO will discuss the relevant issues with the community and restart the process 2 Epochs later with the necessary changes.

**Example Scenario**
* Token listing: There is a request for Token ‘ABC’ to be approved/listed.
* Reserve listings: 
  1. There is a request to add an ABC token reserve. 
  2. There is also a request to add a new bridge Reserve for the USDC token. 
* The Kyber team decides that these new requests will all be put to a KyberDAO vote.
* New KLP will be submitted to Github, and a new KLP campaign will be created to approve:
  * ABC Token
  * ABC Reserve
  * USDC Reserve
* The KyberDAO will vote on whether this KLP campaign will be Accepted or Rejected. 

## Key Considerations:

* There is **no guarantee that approved tokens or reserves will be listed**, since liquidity still needs to be sourced for that token. A token needs at least 1 reserve to be set up to support it. There could also be unforeseen circumstances which prevent certain listings.
* Tokens have to be an ERC-20 token based on Ethereum.
* Each KLP campaign on kyber.org will last 4 days. A campaign can start anytime as long as the start time is at least 4 days before the end of the Epoch.
* KLPs have to be approved by the DAO maintainer (Kyber team) before being scheduled for formal on-chain voting on the KyberDAO.
* The Kyber team will submit the first KLP to facilitate discussions around its framework.
* Please note that KLPs are different from the KIP (Kyber Improvement Proposal) and BRR (Burn/Reward/Rebate) proposals.
* Token and Reserve Listing/Delisting will require a KLP submission.
* The community is highly encouraged to actively discuss all KLPs.
* If required, the Kyber team will help submit a KIP to update the KLP process.
