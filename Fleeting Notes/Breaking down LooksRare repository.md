202206021506
Status: 
Tags: #looksrare 

# Breaking down LooksRare utility libraries
- Utility libraries 
	- OrderTypes
		- Stores listing "maker" details including common listing information within a struct
			- Signer, collection, price, tokenId, amount, etc.
			- Interesting additions are strategy, currency, nonce, minPreceentageToAsk, and signature parameters
		- Includes hash function to compute a bytes32 hash which serves as a key for orders
			- Encodes function signature and arguments
	- SignatureChecker
		- Recovers signer address from signature and signed message (standard ECDSA)
			-  Signature used here is passed in as `uint8 v`, `bytes32 r`, `bytes32 s`
		- Malleability is taken into account already with including the nonce into the hash but extra precautions are taken
			- https://ethereum.stackexchange.com/questions/83174/is-it-best-practice-to-check-signature-malleability-in-ecrecover
		- Supports ERC1271 on top of the standard ECDSA signatures in order to support smart contract wallets like Argent and Gnosis Safe
			- https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/cryptography/SignatureChecker.sol
		- Includes support for EIP712 which includes a domain separator
			- `keccak256(abi.encodePacked("\x19\x01", domainSeparator, hash))`






---
# References
https://etherscan.deth.net/address/0x59728544b08ab483533076417fbbb2fd0b17ce3a#code
