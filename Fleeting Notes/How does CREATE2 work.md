202206071459
Status: 
Tags: #create2 #useronboarding 

# How does CREATE2 work
- Address is calculated as hash of
	- Address of creator
	- Salt provided as parameter
	- Contract creation code
- Specifically `new_address = hash(0xFF, sender, salt, bytecode)`
- Not dependent on nonce or state of creator [[Comparing CREATE2 vs CREATE]]
- Not dependent on contract code but rather creation code
	- Code used to setup contract, which includes constructor and arguments
- Once settled on constructor and arguments, you can pick a salt and have certainty that the contract will be deployed to the address
- CREATE2 powered factory
	- Anyone can deploy a shared contract where its constructor arguments and salt are the same
		- Since the address of the creator is the factory contract, the it allows anyone to deploy the specified contract to the same predefined address
	- Cannot deploy a contract to a predefined address where there is already bytecode (throws immediately)
		- However, this introduces possible upgradeability patterns where the previous contract at the address is `selfdestruct`ed and you can use `CREATE2`
		- Other alternatives like upgradeable proxies are mentioned in [[Upgradeability]]








---
# References
https://blog.openzeppelin.com/getting-the-most-out-of-create2/
https://ethereum.stackexchange.com/questions/97340/can-create2-with-the-same-salt-override-existing-contract
https://github.com/ethereum/EIPs/issues/684