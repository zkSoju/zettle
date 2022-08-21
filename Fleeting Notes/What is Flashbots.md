202208011248
Status: 
Tags: #mev

# What is Flashbots?
- Exends geth client with a service allowing searchers to submit MEV tx without revealing to public mempool
- Prevents tx from being frontrun by generalized frontrunners
- [[Generalized frontrunners copy potentially profitable transactions and submit modified transactions with higher gas]] not as profitable because of routing through flashbots
- Submits transaction to Flashbots relay which submits to miners directly vs broadcasting publicly through p2p gossip process
	- Bundles are successfully completed as a whole or not at all
	- Bundles allow for more specific transaction ordering
	- Any valid tx can be placed inside, including target tx for sandwich attacks
	- Bundles can indicate which block the bundle is valid for 
		- Specific block N+1, N+2






---
# References

