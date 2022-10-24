202208272101
Status: 
Tags: #cosmos

# Dive into Cosmos Academy
- Early background
	- Purpose/application specific blockchains were too siloed and only fit limited use case
	- General purpose blockchains limited to simplistic use case
- Blockchain app architecture
	- Tendermint
		- Accelerates development of distinct blockchains
		- Modules attend to consensus and networking
		- Allows devs to focus on application level 
	- **Blockchain node** - state-machine (Cosmos SDK) + consensus and networking layer (Tendermint Core)
	- Users can stake ATOM with nodes that are reliable
	- Top 150 nodes are validators 
	- Voting power is calculated based on ATOM staked by validator and delegates
		- Determines % of block creation privelege
	- Block either has enough signatures from other validators or it does not which grants absolute finality
		- Unlike PoW with probabilistic finality
	- Avoids centralization because although validation is delegated to a subset of network nodes, users can choose/elect 







---
# References
https://tutorials.cosmos.network/academy/1-what-is-cosmos/blockchain-and-cosmos.html
