202208011847
Status: 
Tags: #mev

# Summary of Flashboys 2.0
- Benefits of DEX over CEX 
	- Self-custody facilitated by smart contracts so funds can't be stolen 
	- Effective price discovery and fair trading through a public ledger
- However DEX's are slow allowing for orders to be *frontrun*
- Reliance on transaction ordering is an anti pattern which leads to the creation of the MEV economy
- DEX design flaws that spawn arbitrage bots
- Focuses 
	- Pure revenue opportunities
		- Subset of DEX arb which consists of multiple transactions occuring atomically with pure profit
		- Simplicity of this opp makes it easy to understand
	- Priority gas auctions (PGA)
		- Arbitrage bots compete against each other b/c pure revenue opps offer unconditional revenue
	- Miner extractable value (MEV)
		- MEV causes systemic consensus vulns because of miners ability to extract value from fees caused by order optimizing (OO)
			- ex. PGA/pure revenue opps
	- Fee based forking attacks
	- Time bandit attacks 
		- Miners rewrite blockchain history to steal funds in the past
- Smart contract security is often studied at application layer making analysis tractable
	- Abstracting away low-level details like miner selection and P2P relayer behavior







---
# References

