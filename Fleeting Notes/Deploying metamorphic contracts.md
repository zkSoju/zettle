202206071551
Status: 
Tags: #create2 #seaport #upgradeability 

# Deploying metamorphic contracts
- Factory contract that reploys contracts with new code to the same address
	- Fixed, non-deterministic init code with CREATE2 opcode
- When undergoing metamorphasis, existing storage is deleted and new contract code replaces old one
- Factory can create metamorphic contracts that utilize a constructor by deploying them with a *transient contract*
	- Transient contract is a proxy approach that is different than the transparent or UUPS approach in that **after each upgrade the storage is wiped** 
	- [[Exploring the three types of proxy patterns]]
- Or you can atomically call an `initialize` function after cloning similar to the transparent proxy

- An immutable CREATE2 factory is also included which does not perform contract redeployments, so it prevents metamorphic contracts from being deployed
	- If contract has already been deployed to the address (specified by init code and salt) by this factory, then prevent redeployment 
	- Otherwise try deployment and if failure then there exists an existing contract








---
# References
https://github.com/0age/metamorphic
