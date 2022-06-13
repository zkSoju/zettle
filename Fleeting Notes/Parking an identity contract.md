202206071427
Status: 
Tags: #create2 #useronboarding 

# Parking an identity contract
- User onboarding is already complex with process looking like
	- Sign up for an exchange
	- Buy crypto with fiat
	- Sign up for a wallet
	- Write down 12 word seed phrase
	- Come up with passphrase
	- Transfer funds from exchange to wallet
- Adding a step to deploy an identity contract will make that experience even more convoluted 
- *Parking* an identity contract solves alot of these issues
	1. Have user sign up for a throwaway EOA address directly in browser (w/out metamask)
	2. User can fund address directly without deploying/creating the identity
	3. Gas station relayer can fund deployment and receive a portion of deposit as customer acquisition costs
- Considered counterfactual instantiation 







---
# References
https://medium.com/tabookey/1-800-ethereum-gas-stations-network-for-toll-free-transactions-4bbfc03a0a56
