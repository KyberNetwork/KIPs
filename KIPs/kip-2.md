---
kip: 2
title: Starting Framework for KyberDAO BRR Process
status: Active
type: Information
author: Kyber Network team
created: 2020-07-12
---

# Starting Framework For KyberDAO BRR Process

### 1. BRR (Burn, Reward, Rebate) ratio will be voted on in every epoch. 

The BRR proposal process will provide a clear ongoing agenda for stakeholders to tweak the status quo, allowing a constant polling of the community and dynamic governance of the network fee allocation. Custom proposals suggesting major updates can be created as part of the Kyber Improvement Proposal (KIP) process. 


### 2. Starting Framework

As the KyberDAO maintainer, the Kyber team has proposed the starting framework for the BRR:

*   There will be 4 options for each BRR campaign, one retaining the status quo, the other 3 preferring one specific parameter
*   Allocation for the new preferred parameter will increase by 5%. 
*   The 5% increase would lead to a corresponding decrease in the % allocation of the remaining two parameters, in accordance to the original ratio between those two parameters.

As such:


<table>
  <tr>
   <td><strong>Options</strong>
   </td>
   <td><strong>Implications</strong>
   </td>
  </tr>
  <tr>
   <td>1/ Status Quo
   </td>
   <td>No updates from current epoch 
   </td>
  </tr>
  <tr>
   <td>2/ Pro-Burn
   </td>
   <td>Burn increases 5% from previous epoch. Rebate and Reward decreases proportionally.
   </td>
  </tr>
  <tr>
   <td>3/ Pro-Reward
   </td>
   <td>Reward increases 5% from previous epoch. Rebate and Burn decreases proportionally.
   </td>
  </tr>
  <tr>
   <td>4/ Pro-Rebate
   </td>
   <td>Rebate increases 5% from the previous epoch. Burn and Reward decreases proportionally.
   </td>
  </tr>
</table>


The exact formula is detailed at the end. The BRR-1, which will be up for voting in epoch 1, will use this formula for calculating the options. 


### 2. The first BRR Proposal: BRR-1

The first proposal on the KyberDAO will be a BRR proposal to decide if there should be changes to the existing network fee parameters. This will start at Epoch 1, on 14th July.  This first BRR proposal will be labelled as BRR-1. 

The current consensus on the initial Burn/Reward/Rebate (BRR) network fee parameters is:



*   B | 5% will be used for purchasing KNC tokens and burning them
*   R | 65% will go to Voting Rewards
*   R | 30% will go to Reserve Rebates for Fed Price Reserves (FPRs)

Based on the BRR framework explained above, we proposed the following four options for the community to vote on during the first BRR proposal in Epoch 1, starting on 14th July. 


<table>
  <tr>
   <td><strong>Option</strong>
   </td>
   <td><strong>Burn %</strong>
   </td>
   <td><strong>Reward %</strong>
   </td>
   <td><strong>Rebate %</strong>
   </td>
  </tr>
  <tr>
   <td>A. Status Quo
   </td>
   <td><p style="text-align: right">
5.0</p>

   </td>
   <td><p style="text-align: right">
65.0</p>

   </td>
   <td><p style="text-align: right">
30.0</p>

   </td>
  </tr>
  <tr>
   <td>B. Pro-Burn (+5%)
   </td>
   <td><p style="text-align: right">
<strong>10.0</strong></p>

   </td>
   <td><p style="text-align: right">
61.6</p>

   </td>
   <td><p style="text-align: right">
28.4</p>

   </td>
  </tr>
  <tr>
   <td>C. Pro-Reward (+5%)
   </td>
   <td><p style="text-align: right">
4.3</p>

   </td>
   <td><p style="text-align: right">
<strong>70.0</strong></p>

   </td>
   <td><p style="text-align: right">
25.7</p>

   </td>
  </tr>
  <tr>
   <td>D. Pro-Rebate (+5%)
   </td>
   <td><p style="text-align: right">
4.6</p>

   </td>
   <td><p style="text-align: right">
60.4</p>

   </td>
   <td><p style="text-align: right">
<strong>35.0</strong></p>

   </td>
  </tr>
</table>


For example, for Option B, the Pro-Burn option, Burn is the preferred parameter, and Reward and Rebate are the remaining two parameters. Burn will increase by 5% to 10%, and Reward will decrease to 61.6%, while Rebate will be 28.4%. 


### 3. Kyber Improvement Proposal (KIP) Framework



*   As the DAO maintainer, the Kyber team is also scoping out a Kyber Improvement Proposal (KIP) framework to allow the community to **discuss and propose changes** for the benefit of the protocol. 
*   The Kyber team will submit the first KIP to facilitate discussions around its own starting framework.
*   Please note that KIPs are unique proposals and different from the BRR proposals, which are more regular and are meant to follow a standard format and process.
*   If required, the Kyber team will help submit a KIP to update the existing BRR process.
*   KIPs have to be approved by the DAO maintainer (Kyber team) before being scheduled for formal on-chain voting on the KyberDAO.
*   Future changes will need to be first proposed as KIPs and reviewed as a community. 
*   The community is highly encouraged to **actively discuss** all KIPs.


### 4. Starting Framework For Determining The BRR Options

**1/ Status Quo**

**2/ Pro-Burn:**



*   New Burn % = Original Burn + 5%
*   New Reward % = Original Reward/(Original Reward + Original Rebate) * [100 - (Original Burn + 5%)]
*   New Rebate % = Original Rebate/(Original Reward + Original Rebate)* [100 - (Original Burn + 5%)]  

**3/ Pro-Reward:**



*   New Reward % = Original Reward + 5%
*   New Rebate % = Original Rebate/(Original Rebate + Original Burn) * [100 - (Original Reward + 5%)]
*   New Burn % = Original Burn/(Original Rebate + Original Burn)* [100 - (Original Reward + 5%)]

**4/ Pro-Rebate:**



*   New Rebate % = Original Rebate + 5%
*   New Reward % = Original Reward/(Original Reward+ Original Burn) * [100 - (Original Rebate + 5%)]
*   New Burn % = Original Burn/(Original Reward + Original Burn)* [100 - (Original Rebate + 5%)]
