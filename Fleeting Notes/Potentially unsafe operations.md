202206011018
Status: #fleeting
Tags: #upgradeability 

# Selfdestruct and delegatecall are not allowed 

- Calling logic contract directly rather than proxy does not pose a threat because state of logic contract is not being used in project
- However, calling `selfdestruct` directly to the logic contract will cause the proxy contract to send delegate calls to an address without code
- If the logic contract can `delegatecall` then it could potentially call `selfdestruct` on itself through a malicious contract
- Therefore, `selfdestruct` and `delegatecall` is not allowed






---
# References

