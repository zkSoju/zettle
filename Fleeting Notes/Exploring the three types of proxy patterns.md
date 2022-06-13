202206011432
Status: #fleeting
Tags: #upgradeability 

# Exploring the three types of proxy patterns
- Diamond pattern (https://eips.ethereum.org/EIPS/eip-2535)
- Transparent proxy pattern
- UUPS - Universal upgradeable proxy standard (https://eips.ethereum.org/EIPS/eip-1822)
	- Pros
		- Gas efficient
		- Universally compatible because it uses a psuedo random storage slot for variable
				-  [[Storage collision with unstructured proxies]]
				- Uses `keccak("PROXIABLE")` instead of a variable to support universal compatibility with all contracts
			- New constructor allows for ability to select from one of many "constructors"
				- `constructor(bytes memory data, address contractLogic) public`
	- Cons
		- Higher risk of new implementations not including `upgradeTo` which would kill the ability to ugprade 

- Difference between transparent and UUPS 
	- Transparent is upgraded through the proxy contract
	- UUPS is upgraded through the logic contract







---
# References
https://blog.logrocket.com/using-uups-proxy-pattern-upgrade-smart-contracts/
