202208021257
Status: 
Tags: #defi

# PGAs, ordering, and HFT
- Tx are routed in a P2P gossip multicast protocol by client node software
	- Tx information available to all participants
	- However, available earlier to participants w/ advantageous positions in gossip topology (closer to client nodes?)
- Nodes can simulate tx outcome
- Mechanics of system make it so that late arbers' tx will fail
- PGA (Priority Gas Auction)
	- Occurs when a arber notices a tx in the network with a higher gas bid
	- Arber then reissues tx with same nonce and even higher gas bid 
	- Auction emerges from the interaction b/w these two parties trying to gain priority in the network
	- Example ![[Pasted image 20220802151746.png]]
	- Nonce remains the same but the gas bids are increasing
	- Losing bid (shown in red) still pays 33547 gas for attempted execution vs. winning bid who pays 113267 gas
		- This called an *all pay* auction where loser pays a portion of the winner




 

---
# References

