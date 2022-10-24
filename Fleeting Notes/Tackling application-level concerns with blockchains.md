202208311156
Status: 
Tags: #cosmos

# Tackling application-level concerns with blockchains
- two approaches
	- create app-specific blockchain where everything that can be done is defined in protocol
		- no language needs to be present
		- layout of storage and state is not implemented as a contract on a state machine (like EVM) but rather properties of a blockchain built for a singular purpose
	- create programmable state machine, which pushes concerns to higher level
		- bytecode created by compilers interpreting higher level languages
		- Ethereum is an example of this
		- limitations
			- very little universally defined
			- contracts can contain repetitive code (issue with high level language?)
			- flexibility make it challenging to reason what is correct







---
# References

