---
kip: 4
title: Enable fees for bridge reserves
status: Active
type: Configuration
authors: Victor Tran, Spyros Vrettos
created: 2020-10-09
---


```
voting_campaign_type: general
voting_start_timestamp: 1602659227
voting_end_timestamp: 1603177627
voting_min_knc_voted_percentage: 40000000000000000
voting_c: 0
voting_t: 0
voting_options: 1, 2
voting_option_titles: "Accept", "Reject"
```


## Summary:

Kyber Network, besides its own formula-based (APR) and FPR reserves, also uses external liquidity venues as a special type of reserves, called bridge reserves, which can pull liquidity from many different external decentralized exchanges to Kyber users.  

Kyber’s APR and FPR reserves are charged network fees whenever trades are performed. However, the external bridge reserves currently contribute 0 fee to the network and their fee_flag is set to False. This KIP proposes that we change the bridge reserves fee_flag to True and allow bridge reserves to be charged the same network fee as APRs and FPRs. This will balance some of the issues currently caused by bridge reserves and also provide additional incentive for the Kyber community (the DAO) to drive more innovation as well as create more bridge reserves. 


## Abstract:

Configure bridge reserves fee_flag to `True` to enable network fees from the trading volume of bridge reserves. This is expected to balance some of the issues currently caused by them and also increase the DAO rewards.

## Motivation:

Kyber started using bridge reserves to bring higher liquidity to the users and Dapps that were integrated with it in late 2018. Since then the landscape has changed. There are several aggregators, which use a variety of methods to discover the most efficient way to route the trades to the best venue(s), also many Dapps are now integrated with the aforementioned integrators directly or with the different trading venues themselves and route the trading flow accordingly. 

Kyber still has external liquidity venues as bridge reserves with 0 fees and we would now like to review their contribution to the network. 

Current issues with bridge reserves:  

1. Reduced fees for the network. At every trade there is a comparison for the rates of reserves, and bridge reserves have 0 fees, contributing 0 fees to the network from their trades. Collected network fee go to KNC holders who staked KNC. 
2. Reducing the sustainability and turnover of the FPRs, from unfair competition. Kyber Network selects the reserve with the best price for a trade and there are higher chances for bridge reserves to execute the trade with better rate since Bridge reserves have 0 fees while FPR is subject to pay the full network fees.  

A case for maintaining 0 fees for bridge reserves can be made if bridge reserves are helping to attract more users to Kyber. A user could choose Kyber's combined liquidity instead of going to an external exchange that might offer worse prices (when Kyber bridges a venue with 0 fees, the price on Kyber is always equal to or better than that venue’s). If we observed the bridged volume on Kyber to be constant or increasing as a ratio of the external exchange's own volume for the same token, this would mean that the bridge reserves do contribute significantly to Kyber's user base, and that many users of other exchanges are actually using them through Kyber, where they might also be matched with other types of reserves (that have fees) for other trades.  

On the other hand, if the bridged volume on Kyber compared to the external exchange’s own volume is decreasing over time, we can infer that maintaining 0 fees for bridge reserves is no longer effective in enlarging our user base. We will discuss our findings from the backing data in the next section.  

Having bridge reserves pay network fees can also encourage the Kyber builder community (who are KNC holders and members of the DAO) to innovate on new bridge reserves to bring more fees and rewards to the DAO.


## Methodology:

We measured volume for DAI token units which is one of the first bridged tokens on Kyber Network how much of the Kyber Network traffic was from bridge reserves. The KN exported data can be found [here](https://drive.google.com/drive/folders/1CIqcFeALVPChpJ7oGRAb8oQWhnXeJ5lt?usp=sharing). A simple [Dune Analytics](https://explore.duneanalytics.com/public/dashboards/02VMomTF7A4TweXeoacHTwMMqCxkAOfNhbqt4JiS) query also contains the results for different exchanges.  
We compare absolute bridged volumes of Kyber through Oasis and Uniswap with Oasis and Uniswap themselves and also the ratio of the volume that was contributed through Kyber. This method shows always lesser comparable volume for bridges because Kyber bridges could only route trades that had ETH as an intermediary and were also including Kyber listed tokens. Still we consider the data enough for our point to be visible.  


## Results:

Date | Kyber Bridged volume<sup id="a1">[1](#f1)</sup>| External Venue volume<sup id="a2">[2](#f2)</sup> |Kyber Bridged volume as % of Total External volume
------- | --------- | ------- | --------:
Feb19| 4.4 |20.5 | 21.5
Mar19| 6.6 |27.3 | 24.0
Apr19| 8.8 |41.0 | 21.4
Jun19| 24.8 |104.9 | 23.6
Jul19| 20.5 |114.6 | 17.9
Aug19| 8.7 |53.9 | 16.2
Sep19| 4.7 |51.7 | 9.1
Oct19| 2.4 |44.9 | 5.3
Nov19| 4.5 |51.2 | 8.7
Dec19| 4.5 |34.0 | 13.4
Jan20| 11.5 |60.2 | 19.0
Feb20| 42.2 |154.6 | 27.3
Mar20| 47.5 |218.4 | 21.8
Apr20| 13.5 |90.8 | 14.9
May20| 12.8 |82.3 | 15.6
Jun20| 13.5 |87.2 | 15.4
Jul20| 15.7 |159.4 | 9.8
Aug20| 17.3 |381.2 | 4.5
Sep20| 34.1 |1116.3 | 3.1

<b id="f1">1</b> Token is DAI and volumes are in millions.  
<b id="f2">2</b> External volume is the combined volume on Oasis and Uniswap.


## Conclusion:

We can see that the percentage of volume routed through Kyber to those other two DAI venues is constantly decreasing. For the last months this is also partly due to the non ETH intermediary and non listed token trades, but the decrease itself shows that the positive effects from attracting takers and users that are not directly matched on Kyber are diminishing. This means that takers are either integrated with the other venues or using them directly or using intermediaries that route the trades for them.  

Overall, the positive arguments that one would make for maintaining 0 fee bridges are not enough to counterbalance the negative effects described earlier.  

Moreover, enabling network fee for bridge reserves will lead to more rewards for the DAO and encourage token teams to contribute liquidity to Kyber directly, while incentivising the Kyber community (the DAO) to drive more innovation for bridge reserves.

For the above reasons we suggest that bridge reserves start being charged fees on the network.

KIP-4 submission is contingent upon the prior approval of [KIP-3](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-3.md).

##### Rationale:
- KIP-3 proposes a reduction of network fees from 20bps to 10bps for FPRs and APRs. This helps mitigate the new fees proposed for bridge reserves in KIP-4. Without KIP-3, total network fees might become overbearing and much less competitive.
