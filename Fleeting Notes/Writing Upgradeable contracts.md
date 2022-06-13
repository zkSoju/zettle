202205311251
Status: #fleeting
Tags: #upgradeability 

# Initializing upgradeable contracts
- No constructors can be used because of proxy based system
- Function called `initialize` contains all setup logic
- Ensure initialize can only be called once using a `bool` to simulate constructor
- `Initializer` needs to initialize all parent contracts `initialize` because functions operate differently than constructors in that they don't automatically invoke the constructor of ancestors
- Contracts that are being imported like `ERC20` also need to follow the upgradeability patterns because they contain constructors
- Initial values should be set in `initialize` not when declaring them in contract
- Constant is **OK** because they are not in storage, but in bytecode









---
# References
https://docs.openzeppelin.com/upgrades-plugins/1.x/writing-upgradeable
