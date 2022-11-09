202211081844
Status: 
Tags: #eip #eip4337

- Abstraction proposal avoids consensus layer protocol changes
- Higher layer psuedo transaction object `UserOperation`
	- Sent to a separate mempool
	- Alt mempool bundles tx and makes a `handleOps` call 
	- Transaction is incl. in block
- Motivation
	- Achieve the key goal of account abstraction
		- Remove need for EOAs
		- Users can use arbitrary verification logic 
	- Decentralized 
		- Any bundler can participate in including abstracted operations
		- Abstract direct communication process, IP/Onion (with alt mempool?)
	- Does not require consensus changes 
	- Try to support other use cases
		- Privacy apps
		- Atomic multi operations
		- Pay tx fees with ERC20/allow devs to pay fees for users
		- Aggregated signatures (BLS)
- How does it work?
	- ABI struct `UserOperation` -> bundlers (ex. Flashbots) listens into pool and creates tx -> 








---
# References

