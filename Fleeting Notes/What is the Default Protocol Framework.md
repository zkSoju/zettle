202210261543
Status: 
Tags: #protocoldesign

- Many protocols today architect smart contracts by building out one step in logic at a time
- This results in long and convoluted chains of processes 
	- Hard to understand
	- Difficult to audit (inevitable human error)
	- Prone to security risks and exploits
	- Heavy documentation is required for understanding
- This makes it difficult for developers to contribute to an existing codebase due to lack of overall understanding and learning curve required
---
- The goal of the protocol framework is to build protocols and **write contracts around data models rather than processes**
	- Benefits
		- Easy to make assumptions about intended behavior without familiarizing with the codebase
		- Removes potential for long or circular dependencies
- Building with the Default framework
	- Contracts are either modules (backend) or policies (frontend)
	- Modules (*what* data models exist? *how* can they be modified?)
		- Internal facing sharing stored state across protocol (similar to microservice)
		- Can only modify their own internal state
		- Can only be access through whitelisted policy contracts
		- No dependencies of their own
	- Policies (provides context for *why* do these changes happen?) 
		- External facing contract that receive inbound calls
		- Routes updates to data models via modules
		- Business logic is composed here
- Example: NextJs frontend -> Transaction (external interaction) -> Protocol frontend (policies) -> Protocol backend (modules)
	- Acts similarly to an API
- ERC20 could be an example of a module
	- Define data model around account balances `balanceOf`
	- Include functions that define how account balances can be changes `transfer()`, `mint()`, `burn()`
	- Include miscellaneous functions like `totalSupply()` to aggregate amount of balances
	- Key points
		- Data changes are limited to internal state - nothing happens outside 
		- What about policies? Well, permissionless functions like `transfer()` can be called directly by  user
		- Default applies more to permissioned functions like `mint()` and `burn()` where it is more applicable
- Default leaves control up to the developers about where to put functions: atomically in the module where it can be called by users or permissioned in the policies where it can only be called by specific users







---
# References
https://github.com/fullyallocated/Default
