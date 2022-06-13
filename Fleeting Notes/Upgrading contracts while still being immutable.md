202206011410
Status: #fleeting
Tags: [[Literature Notes/Upgradeability]]

# Upgrading contracts while still being immutable
- Access point/proxy address is never changed
- Logic contract cannot be changed, but is swapped out such that the proxy address points to the "new" logic contract
- Simulates the "upgrade" of software

```
User ---- tx ---> Proxy ----------> Implementation_v0
                     |
                      ------------> Implementation_v1
                     |
                      ------------> Implementation_v2
```







---
# References

