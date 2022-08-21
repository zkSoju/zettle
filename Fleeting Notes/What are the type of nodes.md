202208181521
Status: 
Tags: #ethereum 

# What are the type of nodes
- Full node
	- Stores full blockchain data
	- Participates in block validation
	- All states can be derived from full node
	- Serves network and provides data on request
- Light node
	- Stores only block headers containing information about contents
		- Additional information is requested from full node
	- Allows normal users to participate in networ without powerful hardware or high bandwidth
	- Don't participate in consensus, can't be miners/validators
	- Not well developed because it largely requires full nodes to serve light node data which many opt out of
- Archive node
	- Stores everything kept in full node to simply test without mining using tracing
	- Popular for block explorers, wallet vendors, etc.






---
# References

https://ethereum.org/en/developers/docs/nodes-and-clients/