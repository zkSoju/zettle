202208091302
Status: 
Tags: #mev

# Understanding bundle pricing with Flashbots
- Blockspace is limited and searches submit huge amount of bundles
- Flashbots designed such that miners include most profitable tx in blocks by inserting searcher bundles at top and removing tx at tail of block
- Gas price at tail are low/least profitable to mine 
- Flashbots bundle is profitable when gas price than tx at the tail
- Why aren't bundles being included?
	- Bundles may not be paying higher gas price than tail end
		- Should simulate before hand to get coinbase difference and gas consumed
	- May be competing with other searchers who are paying higher gas price
	- Minimum 42000 gas otherwise rejected by relay







---
# References
https://docs.flashbots.net/flashbots-auction/searchers/advanced/bundle-pricing
