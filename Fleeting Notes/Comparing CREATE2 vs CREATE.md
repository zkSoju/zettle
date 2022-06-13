202206071128
Status: 
Tags: #solidity #evm #create2

# Comparing CREATE2 vs CREATE
- `CREATE2` opcode gives us the ability to predict address where a contract is deployed without deploying
- Improves user onboarding and scalability
- When creating a contract from an EOA/contract account with the standard `CREATE`  it is easy to determine the deployment address
	- EOA -> Nonce is increased with each tx sent 
	- Contract account -> Nonce is increased with contract deployed
- `CREATE` address computed as `address = hash(sender, nonce)`
	- Allows for ability to know address in advance but *parking* an address is difficult
		- **Parking** - ability to reserve address for contract regardless of transactions sent in meantime
	- No other contract must exist at the address, so you can use the expected nonce
- One motivation of `CREATE2` is [[Counterfactuality with CREATE2]] which allows us to refer to a contract address before being deployed
- Primary use case is [[Receiving funds without a wallet or being a part of the network]]







---
# References
https://docs.openzeppelin.com/cli/2.8/deploying-with-create2
https://blog.openzeppelin.com/getting-the-most-out-of-create2/