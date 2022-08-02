202208011257
Status: 
Tags: #defi #mev

# Lending protocols liquidations introduce a MEV opportunity
- Maker and Aave lending protocols require collateral deposits in order to borrow against deposit in a different asset 
	- ex. deposit ETH and borrow MKR for voting or SUSHI for staking and earning trading fees
	- Borrowing power percentage determined by protocol
- If market fluctuations cause borrowed assets exceeds x% of value of collateral, protocol allows user to liquidate collateral (ex. ETH) to pay off lenders (margin call in tradfi)
- If liquidated, borrower has to pay hefty liquidation fee which goes to liquidator (this is where mev opp comes in)
- Searchers parse blockchain data to determine which borrowers can be liquidated and submit liquidation tx to collect liquidation fee








---
# References

