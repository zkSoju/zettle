202205311307
Status: #fleeting
Tags: #upgradeability 

# How do proxies work?
- Delegate calls to logic contract
- Proxies require a function `upgradeTo(address)` to change the logic contract to point to
	- What if the logic contract also has the same function name?
		- Function clashing occurs when 4 byte function signature matches and compiler warns occurence when in the same contract
		- When in different contracts it does not
		- So how to distinguish if user wants to call local or delegate?
- Transparent proxy pattern
	- If owner of proxy, proxy will **not** delegate
	- If not owner of proxy, proxy will **always** delegate
	- Proxy `owner()` and `upgradeTo()` / ERC20 `owner()` and `transfer()`
	- ![[Pasted image 20220531131821.png]]
- Intermediary ProxyAdmin contract is created, which is owner of all proxies so you don't have to worry about this pattern
	- Allows any node account, even deployer, can interact normally






---
# References
https://docs.openzeppelin.com/upgrades-plugins/1.x/proxies#the-constructor-caveat
