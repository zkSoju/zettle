202207081928
Status: 
Tags: #ethers

# Understanding ethers terminology
- General purpose library to interact with Ethereum blockchian and its ecosystem
	- Provider
		- Class that provides abstraction for a connection to the eth network and **provides read-only access** to the blockchain
	- Signer
		- Class which **directly or indirectly has access to private key**
		- **Can sign messages and transactions** to authorize the network to charge ether to perform operations
	- Contract
		- Operations
- Connecting to ethereum through Metamask
	- Metamask provides both a **provider** and a **signer**
	- `new ethers.providers.Web3Provider(window.ethereum)` wraps the standard Web3 provider which Metamask injects at `window.ethereum`
	- `await provider.send("eth_requestAccounts",[])` to request permission to connect users acccounts
	- Fetch the signer with `provider.getSigner()`
- Connecting to ethereum through RPC
	- Available as node implementations (Geth/Parity) and third party web-services like Infura
	- Providers both a **provider** and a **signer**







---
# References

