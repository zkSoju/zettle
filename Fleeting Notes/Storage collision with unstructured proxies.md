202206011421
Status: #fleeting
Tags:

# Storage collision with unstructured proxies
- When variables are stored in the proxy contract, we can run into an issue where storage slots overlap between the proxy contract and logic contract
- Issue arises from the way `delegatecall` works
	- Storage writes (and state changes?) are made in the context of the proxy contract
```
|Proxy                     |Implementation           |
|--------------------------|-------------------------|
|address _implementation   |address _owner           | <=== Storage collision!
|...                       |mapping _balances        |
|                          |uint256 _supply          |
|                          |...                      |
```
- EVM writes both variables into the same slot
- Openzeppelin tackles this by psuedo randomizing the storage slot to store the logic contract address
	- This principle is used in other locations as well to prevent interference
```solidity
bytes32 private constant implementationPosition = bytes32(uint256( keccak256('eip1967.proxy.implementation')) - 1 ));
```
- Other implementations require the proxy contract being aware of the structure of the logic contract or vice versa
	- Which is why this approach is called **unstructured storage**
- Unstructured storage prevents collisions between proxy and logic, but not logic and logic
	- For that you need to follow [[Caveats to adding new features or fixing bugs through upgrading]]





---
# References

