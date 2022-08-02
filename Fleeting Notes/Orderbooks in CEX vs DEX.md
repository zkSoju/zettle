202208011948
Status: 
Tags: #mev #dex
 
# Orderbooks in CEX vs DEX
- Continuous order books in a CEX
	- Limit buys and limit sells
	- Centralized party matches the two and processes in order received
- In a traditional DEX, order books are offchain and order processing is done by the smart contract
	- Some designs have parties find a signed counterparty order and present it to a smart contract to execute (similar to a NFT marketplace)
		- Here a trader does the order matching
	- AMMs are a new paradigm for decentralized protocols
		- Bypasses order books
		- Protocol holds reserves of asset pool pairs A and B
			- Amount of reserves determines rate (think Uniswap) so every trade will affect the rate
			- Constant arbitrage is required for price discovery
			- Single parties can trade without price discovery or matching







---
# References

https://app.uniswap.org/#/swap?chain=mainnet
https://sudoswap.xyz/#/