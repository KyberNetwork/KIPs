---
kip: 3
title: Change network_fee from 20 to 10 bps
status: Active
type: Fee
authors: Victor Tran, Spyros Vrettos
created: 2020-10-02
---

```
voting_campaign_type: fee
voting_start_timestamp: 1601968027
voting_end_timestamp: 1602572827
voting_min_knc_voted_percentage: 40000000000000000
voting_c: 0
voting_t: 0
voting_options: 10, 20
voting_option_titles: "Reduce network fee to 10bps", "Keep network fee as 20bps"
```


## Summary

In recent past, formula-based liquidity venues built around passive market makers have seen a huge inflow of passive liquidity. Kyber Network’s predominant source of liquidity comes from professional market makers using FPRs (Fed Price Reserves). With several billions of dollars worth of inventory passively providing liquidity for the major ETH pairs in AMM protocols, it is harder for Kyber to have the largest liquidity share for the major ETH pairs. By reducing network fees to optimal levels, Kyber FPRs can offer better prices for the takers, and therefore increase volumes which in turn generate more fees. 

This KIP suggests lowering the overall network fees from 20bps to 10bps with the purpose of increasing Kyber’s volume share, subsequently increasing the overall network fees while further supporting the sustainability of Kyber's FPRs.

## Abstract

Change the `network_fee_percentage` parameter of the Kyber ETH Network (learn more about what it is [here](https://github.com/KyberNetwork/KIPs/blob/master/KIPs/kip-1.md#network-fee)) from 0.2% (20bps) to 0.1% (10bps). This is expected to bring more overall fee to the network by claiming more volume from other liquidity venues. Increased volume will also help on the sustainability of Kyber FPRs.


## Motivation

After the recent changes in the tokenomics of different AMM venues that resulted in billions in TLV for the major ETH pairs, we see the following:  

1. Often worse taker rates for Kyber in the major (stable,WBTC) /ETH pairs
2. Increased overall gas costs due to higher gas prices that are also existent because of the many arbitrage opportunities that are currently presented in AMMs. This also resulted in:  
	1. Increased gas costs for the FPRs to maintain prices
	2. Increased gas costs for the takers of the network since Kyber matching has higher gas usage, thus making trading small amounts less efficient
3. Reduced volume for the network since aggregators, arbitrage bots and other price-sensitive takers use Kyber less. This results in:  
	1. Reduced fees for the network
	2. Reduced trading volume for the FPRs, which combined with the increased gas costs for maintaing the prices, challenges their profitability and sustainability in the long run.
	
The fastest and the most direct way to react to this situation is to lower the network fee.

## Backing data analysis
### Methodology
We measured the trade sizes on Uniswap and Kyber for USDC and WBTC which are two representative high volume and liquidity pairs. Trade size data can be found [here](https://drive.google.com/drive/folders/1jMgmnAusjQG0Vqv5SQRFRmG1nXaFfCAC?usp=sharing).   
- Kyber 95 and 98 percentile transaction size is 168 and 268 eth. Median is 30 eth.
- Uniswap 95 and 98 percentile transaction size is 100 and 200 eth. Median is 4 eth.
With those results in mind, we decided to query rates for up to 200 eth equivalent amounts. 

We examined rates for the pairs WBTC/ETH and USDC/ETH for September 2020. We compared Kyber FPR reserves rates with Uniswap rates. We polled data from the network every 20 blocks and compare the BUY and SELL prices for [1,20,50,100,200] ETH equivalent amounts. We break September into two periods: 1st-17th and 17th -30th. Twose two periods correspond roughly to the change in the liquidity ([source](https://uniswap.info/pair/0xbb2b8038a1640196fbe3e38816f3e67cba72d940)). Beginning of September has a record TLV, but the 17th-30th is the period with even more TLV. When doing *token to eth* we used as token input amount per eth the amount that Uniswap would return for converting 1 eth to token. This way both Kyber and Uniswap used same input amounts. Rate data can be found [here](https://drive.google.com/drive/folders/1Ei4ph5TYuvNljO-PaOArK0k9wTFECvmX?usp=sharing). Kyber rates in the dataset contain a 20bps fee from the network. For this example only Kyber FPRs where chosen to compare with Uniswap and not other integration reserves or AMMs. Furthermore many times not all FPRs where quoting rates because of high gas usage.  

### Data Results

- USDC results with *1, 20, 50, 100, 200* ETH amounts:

Date range | Fee | % of time with better ASK price | % of time with better BID price
------- | --------- | ------- | --------:
01-17 Sept | 20 | 50, 50, 49, 45, 35 | 29, 26, 24, 20, 15
01-17 Sept | 15 | 55, 55, 54, 49, 40 | 33, 29, 27, 23, 17
01-17 Sept | 10 | 59, 59, 59, 54, 45 | 37, 33, 31, 26, 20
17-30 Sept | 20 | 41, 39, 36, 31, 21 | 32, 27, 25, 20, 15
17-30 Sept | 15 | 47, 45, 42, 35, 26 | 38, 33, 30, 24, 18
17-30 Sept | 10 | 52, 50, 48, 41, 31 | 43, 38, 35, 28, 22

- WBTC results with *1, 20, 50, 100, 200* ETH amounts:

Date range | Fee | % of time with better ASK price | % of time with better BID price
------- | --------- | ------- | --------:
01-17 Sept | 20 | 37, 40, 50, 64, 73 | 32, 37, 48, 63, 70
01-17 Sept | 15 | 40, 43, 53, 67, 74 | 36, 41, 52, 66, 72
01-17 Sept | 10 | 43, 47, 57, 69, 75 | 40, 45, 55, 68, 74
17-30 Sept | 20 | 43, 37, 33, 27, 17 | 28, 23, 17, 13, 06
17-30 Sept | 15 | 47, 42, 37, 32, 21 | 31, 26, 21, 17, 09
17-30 Sept | 10 | 52, 46, 42, 35, 25 | 35, 29, 23, 20, 12

Based on the data results, with the new reduced fee of 10bps, we can expect much better ASK and BID prices on Kyber. This will in turn lead to higher volume and more network fees collected overall. 

## Conclusion

We see that at the beginning of the month where the passive LPs were contributing a lot of liquidity due to the token model introduced from Sushi it was harder to provide better liquidity, especially in the larger size trades. This is more prominent after the 17th where the difference for large quantity trades becomes even bigger due to the new token model by Uniswap. The 10bps over 15bps improvement seems marginal, but one has to take into account the increased capacity for price improvements that Kyber FPRs will have with the greater turnover. For the above reasons changing network fees to 10bps is suggested.  

Additionally, a 10bps fee is more alligned with the current DeFi platform fees. This change is supposed to help the network have more fees by lowering the fee percentage but expecting to have bigger turnover, also contributing to the sustainability of -currently- the main liquidity source of Kyber ([source](https://blog.kyber.network/kyber-ecosystem-report-18-dae7422673c6)), the FPR reserves.
