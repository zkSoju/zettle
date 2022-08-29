202208272040
Status: 
Tags: #cosmos

# Anatomy of Cosmos SDK application
- Node client (full node) is core process of blockchain
- Participants in network run process to init state, connect with other nodes, update state with incoming blocks
- Typically suffixed by `-d` for daemon (ex. `appd`)
- `start` command on a node
	- Creates instance of state machine
	- Initialize state machine with latest known state
	- Create tendermint instance
		- Perform handshake to receive latest height
		- Replay blocks to sync to new height
		- If local block height is `0`, `InitChain` message is sent triggering `InitChainer`





---
# References

