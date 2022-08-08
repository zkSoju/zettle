202208041454
Status: 
Tags: #mev

# What are some PGA strategies?
- Three types
	- *Blindraising* and *Counterbidding* which are usually in competition with each other
	- *Cooperative*
		- Probably not perfect coordination because otherwise on-chain bidding wouldn't be needed
- Latency wars
	- Lower latency gives advantage
- Blind raising 
	- Non-adaptive strategy
	- Increases by fixed increments
	- Seems bad because they fail to exploit information available to play in B
	- Howwever non-adaptiveness/imperfect information compared to natural adaptive strategies creates an advantage because of network latency
		- Player can publish bid faster than by waiting to see opposing bid
- Counterbidding
	- Player observes opponent bidding strategy and reacts
	- Involves outbidding as quickly as possible by small amount higher than required minimum
- Cooperation
	- Common pattern where players slowly alternate raising bids
	- Offchain cooperation where a single bid is made onchain is unlikely
	- Experimental game theory where participants in wild will converge to equilibrium
	- Grim trigger equilibilrium
		- Any defection is responded to by immediately bidding max amount (eliminates all profitability)
		- If a player becomes non-cooperative and deviates by bidding too soon/raising bid higher than usual then other player can effectively end the auction
	- Minimum bid raises
		- All players are incentivized to keep bid price as low as possible to maximize profit
	- Nash equilibrium
	- Each player raises bid by 12.5% implying that within 17 rounds entire auction reward is given to miners







---
# References

