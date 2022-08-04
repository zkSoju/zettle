202207301918
Status: 
Tags: #defi

# What is DAI and how does it work?
- Huge price flucuations prevent widespread adoption
	- Collateralized debt position (CDP) offers possible solution to high volitality
- Stablecoin is a cryptocurrency pegged to another asset
- DAI offers stability, transparency, and decentralization
	- Built on smart contracts that stabilize Dai through a series of dynamic feedback systems (CDP)
		- User deposits asset as collateral for a loan
		- User receives USD value in Dai that they wish to borrow
		- User will pay back Dai plus interest to receive collateral back
	- Stability allows you to invest in a non-stable asset and maintain amount in ETH
	- CDP must hold higher collateral than debt otherwise risk of liquidation
- Uses Pooled Ether (PETH) which allows CDP to retain higher value of collateral than debt
	- If ETH crashed than debt in CDP would be worth more than collateral held
	- Maker can decrease supply of PETH -> increase demand -> increase price of Dai
- Target Rate Feedback Mechanism (TRFM)
	- Example: if fixed peg ratio drops below 1:1, generation of Dai decreases to increase price of Dai
- Maker requires realtime information to be fed through oracles in order for autonomous procedure to work
- Ensures CDP collaterals are worth more than debt, otherwise TRFM kicks in to level price of Dia
- Global settlement is a last resort to guarantee target price
	- Shuts down system
	- Holders of Dai receive net value of assets
	- Maker votes govern access to it in case of emergency






---
# References
https://medium.com/mycrypto/what-is-dai-and-how-does-it-work-742d09ba25d6
