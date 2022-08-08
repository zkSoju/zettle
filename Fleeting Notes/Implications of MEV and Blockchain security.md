202208081156
Status: 
Tags: #mev

# Implications of MEV and Blockchain security
- PGA and DEX arb may not seem harmful or relevant to blockchain security
- However they present security risk at consensus layer
- Application layer security poses a current risk to consensus layer security
- In stable blockchain, block rewards incentivize honest behavior
	- However **order optimization** fees which miner can reap from control of consensus epoch can incentivize **forking attacks**
	- OO fees can be captured by reordering tx and potentially inserting their own
- [[Is OO an issue with PoS and the merge]]
- Profit available in systems from MEV can subsidize forking attacks
	- Undercutting attack
		- Fork block with significant MEV
	- Time bandit attack
		- Fork blockchain retroactively based on past MEV
		- Threat bc it leverages not only OO but also any MEV that can be obtained by *rewinding* a blockchain
		- Any high MEV system generates an inherent threat to stability of PoW
			- Larger they grow, bigger the threat
- Fixed miner rewards is a key feature of secure protocol
	- When rewards are based on fees within the block, miner can fork a high fee block
		- Book "On the Instability of Bitcoin Without the Block Reward" refers to block rewards going to zero
- Undercutting attack
	- OO fees are a form of value that dominates explicit tx fees today
		- Possible sources
			- Sophisticated arb
			- Stealing arb
			- Buy into profitable ICO/NFT
			- Manipulation of games of chance
- Time bandit attack
	- Difficult to pull of because 51% collusion required?
	- Masive mining resources required
		- Rental attacks feasible using cloud resources with GPUs
	- Use MEV from past blocks via rewinding 
	- How to execute
		- Current block has stealable value that exceeds block rewards
		- Adversary can rewind to previous block and take MEV to finance 51% attack that mines fork up to current block
	- In light of PoS upgrade, ETH miners may be incentivized to collude for short term profit
	- Example
		- 1 USD to 3 USD spike on an onchain AMM
		- Attack can acrue entire 1M volume of token prior to spike by rewinding 24 hours of history
		- Results in 2M gross MEV profit
		- In 2019, 24-hour 51% rental attack costs 1.78M which results in net profit 220K
	- Doesn't only apply to DEX, any profitable action in the past is a potential source for attack
	- Currently suggests that 56M is required to execute this attack when DEX volume show a peak of 1.5B







---
# References

