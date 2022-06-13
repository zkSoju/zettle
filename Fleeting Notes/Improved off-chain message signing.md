202206021539
Status: 
Tags: #eip #eip712

# Improved off-chain message signing (EIP-712)
- Structured and readable message signing
- Before EIP712 messages were unreadible as a hexadecimal string
	- Cannot easily verify that the hash is truly the hash of their intended order
- Domain separator used to prevent signature collisions between dApps that might use the same struct/message
- Uses ChainID from https://eips.ethereum.org/EIPS/eip-155
	- Used to have to hardcode the chain id, but since Solidity 0.8.0 you could access with `block.chainid`
		- https://github.com/ethereum/solidity/pull/10557







---
# References
https://medium.com/metamask/eip712-is-coming-what-to-expect-and-how-to-use-it-bb92fd1a7a26

https://eips.ethereum.org/EIPS/eip-712
