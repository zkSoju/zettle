202206071206
Status: 
Tags: #create2 #useronboarding

# Receiving funds without a wallet or being a part of the network
- Key component in user onboarding flows
	- Empowering but intimidating to have full responsibility of custody of your own funds
	- `CREATE2` makes it as easy to generate a contract address as it is to generate private keys
		- Allows users to start with storing funds in a contract
			- Enables more recovery options
			- Multi-device support scenario because keys are never exposed
		- Keys should provide access **not** hold funds
	- Reserved addresses
		- Imagine a traditional signup with where key pair and contract address is also created
			- Address can receive funds but is inaccessible until contract deployment
			- "Receiver does not need to be part of the network to receive funds" (similar to PayPal/Zelle)
		- Very similar to how addresses are represented in [[Introduction to Cairo]]
- New user onboarding flow
	1. User generates key locally
	2. Key generates contract address
	3. Funds sent to address prior to deployment
	4. Contract deployed after user has enough to pay for gas
	5. For beginner users, centralize key recovery
- Interesting point is that sending funds to EOA which uses the "deposit" function would instead just be "transfer" between addresses 
- Allows users to have flexibility in their recovery options and "self-custody" tolerance
	- **Centralization may be acceptable as long as the user has self-custody and can exit at anytime**






---
# References
https://blog.goodaudience.com/one-weird-trick-to-fix-user-on-boarding-d54b7ff9d711
https://blog.openzeppelin.com/getting-the-most-out-of-create2/