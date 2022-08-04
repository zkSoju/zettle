202208041251
Status: 
Tags: #mev

# Diving into PGAs between miners and bots
- Model properties
	- Continuous time
		- Blockchain networks are async 
	- Imperfect information
		- Players eventually see one another's bids but not instantly (latency)
	- All pay
		- Losers pay gas costs for failed transactions
	- Probabilistic auction duration
		- Termination at random time (next block mined)
	- Rate-limited bidding
		- Throttling by p2p networks to prevent flooding attacks requires users to wait an interval before increasing bid
	- Minimum starting bid
		- There is no required minimum but to be included in the block it cannot be too low
	- Minimum bid increments
		- Gas must be increased by at least minimum threshold to be relayed 







---
# References

