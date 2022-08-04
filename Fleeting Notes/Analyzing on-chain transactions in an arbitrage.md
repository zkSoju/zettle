202208021537
Status: 
Tags: #mev

# Analyzing on-chain transactions in an arbitrage
- Difficult to analyze PGA with on-chain data because transactions other than the "winner" discarded
- Tx replaced too fast and are not propogated to nodes
- No tools available so geth was forked to record unconfirmed tx in the mempool
	- Infeasible to track every tx so high value gas replacement tx were traced
- Does profitability persist in competitive environments b/w bots or does it become a zero-sum game?
	- Majority of PGAs are zero-sum however many see relatively zero costs 
	- Profit distribution provides mean profit to winning bots
- Innovation of more complex sophisticated exchanges opens the doors for more complex opportunities
	- More trades in a single transaction as complex opps arise
		- Liquidity pooling (Kyber) which uses an exchange contract to trade  on another exchange
- Some users typographical errors can be attributed to poor exchange usability and flawed market design







---
# References

