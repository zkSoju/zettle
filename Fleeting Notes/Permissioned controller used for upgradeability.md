202205281613
Status: #fleeting
Tags: #seaport #upgradeability 

# Permissioned Controller used for upgradeability

- `conduitController` is an optional contract that is used as a manager of conduits
	- **Conduits** represent contracts that is allowed to transfer approved tokens on the behalf of callers
	- Core contract is not owned by anyone, so contract provides some level of control to stop the breaks if needed in order to keep funds safe
	- Allows for upgradeability without everyone needed to reapprove new contracts
	- Example: Seaport and Opensea could be added/approved as a conduit
		- Users can either:
			- Trust and approve the `conduitController` once
			- Reapprove individual conduits everytime it upgrades







---
# References
[[About Seaport]]