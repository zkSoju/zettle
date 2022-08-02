202208011939
Status: 
Tags: #ethereum 

# Gas and fees in Ethereum
- A transaction
	- Either sends money to a *non-executing* EOA (account address)
	- Sends input data to a smart contract address
- Tx gossiped to all nodes to signal availability to be included in block
- Possible states
	- Unconfirmed
	- Confirmed
	- Rejected
- Gas is consumed as execution cost for computation
- Gas price * gas units consumed = gas fee
- Gas limit determines max steps node should attempt before rejecting
	- Prevents DoS and other attack vectors
	- Allows estimation of fees to ensure user have sufficient funds
- Clients can do a *gas replacement*
	- Re-submit tx with higher tx fee
	- Blockchain only can include one (address, nonce) pair 
	- Unconfirmed tx is resubmitted with same nonce and higher tx fee causing miner to prefer higher fee and replace old one






---
# References

