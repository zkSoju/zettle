202206011413
Status: #fleeting
Tags: #upgradeability 

# Routing functions through the proxy
- How do we expose the entire interface of any contract through a proxy?
	- A one-to-one mapping of every function is infeasible and makes the interface non-upgrade
```solidity
assembly {
  let ptr := mload(0x40)

  // (1) copy incoming call data
  calldatacopy(ptr, 0, calldatasize)

  // (2) forward call to logic contract
  let result := delegatecall(gas, _impl, ptr, calldatasize, 0, 0)
  let size := returndatasize

  // (3) retrieve return data
  returndatacopy(ptr, 0, size)

  // (4) forward return data back to caller
  switch result
  case 0 { revert(ptr, size) }
  default { return(ptr, size) }
}
```
- We can use a fallback method to forward any function (any parameters and return) to the logic contract without any need to know about the functions that it contains
	1. `calldata` is copied to memory
	2. call is forwarded to logic contract 
	3. return data from call is retrieved
	4. return data is forwarded to seller






---
# References

