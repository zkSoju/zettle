202208091031
Status: 
Tags: #mev

# Arbitraging low risk gains atomically
- Buy asset on one exchange and selling on another for higher price
- Positive mechanism that keeps markets efficient and reduces price discrepancies
- Atomic arbitrage
	- Involves bundling onchain interactions allowing which enables "all or nothing" execution
	- Differs from tradfi arb in that this execution allows you to incur zero risk because there are no race conditions
	- Can also code smart contract bundler to assert that end balance is greater than starting to ensure that profit is made
- Atomic execution enables novel economic mechanisms not available in trad computing
	- **Flashloans and flashswaps** which don't require collateral to be secured like in trad loans
		- Allows for borrowing and returning loaned assets in one execution/tx
	- Enables you to leverage millions of extra capital to execute an arb and keep profits
	- Capital intensive strategies are now available to anyone
- CEX Arbs work similar to trad forex arbs
	- In order to capitalize on arb opp, you need variety of assets on both exchanges because by the time you want to withdraw opp may be gone already







---
# References
https://calblockchain.mirror.xyz/c56CHOu-Wow_50qPp2Wlg0rhUvdz1HLbGSUWlB_KX9o
