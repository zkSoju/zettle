202211011127
Status: 
Tags: #protocoldesign 

- Entire contract set is considered a cohesive unit
- Upgrade the entire set instead of individual contract code
- Kernel.sol, a contract registry, manages the set in a single contract
	- Provides functions for
		- Approving a policy
		- Terminating a policy
		- Installing a module
		- Upgrading a module
	- Policies are approved/terminated through a whitelist which authorizes a policies usage of modules
	- Modules installed/upgraded are mapped from address to a 3 letter keycode (ex. "TKN" for token module or "TSY" for treasury module)
		- Modules cannot be removed, only upgraded, which ensures backwards compatibility 
			- Won't break existing systems that rely on contracts
- The executor
	- Executor is address with permission to execute instructions (owner of Kernel)
	- Initial executor is deployer of Kernel 
	- Can be changed with `changeExecutor()`
	- "GPU" optional modules allows for multicall








---
# References
https://github.com/fullyallocated/Default