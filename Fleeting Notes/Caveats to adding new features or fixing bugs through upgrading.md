202206011022
Status: #fleeting
Tags: #upgradeability

# Caveats to adding new features or fixing bugs through upgrading
- Cannot change order of declarations of state variables 
- Cannot change types of state variables
- If you need to add a variable, it has to be at the end
- You can not reorder base contractsbecause it will reorder how state variables are stored
- You cannot add new variables to base contracts if child has variables of its own

```solidity
contract Base { uint256 base1; } 
contract Child is Base { uint256 child; }
```
- Bypass is to reserve slots in the base contract for future user






---
# References

