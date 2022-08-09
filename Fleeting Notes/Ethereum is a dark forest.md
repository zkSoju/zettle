202208081301
Status: 
Tags: #mev

# Ethereum is a dark forest
- Dark forest 
	- Civilization is separated by huge stetches, resources are scarce, creating ultimate competition
	- Public identifying location of someone is sure death to advanced predators
	- Eth mempool, apex predators are arb bots
		- The best Arb bots must monitor all pending tx and attempt to exploit opps with speed
		- Generalized frontrunners can copy any profitable tx 
- Calling `burn` and to extract the free money could signal a generalized frontrunner to frontrun the tx
- Free money sitting on-chain for 8 hours but any attempt to take it would get sniped inflight
- To extract without bot detection, would need to alter tx so call wouldn't be detected
	- Plan was to bury the call internally in another smart contract
		- `Setter` contract sets `Getter` contract which will call `burn` only when `set`
		- `set` and `get` called within the same block
	- Attacker would have to call both `set` and `get`
		- By the time they notice, tx should already be included
	- Authors failed to execute the `get` which was eventually sent into a later block after multiple attempts
	- `get` was eventually included but error was returned meaning liquidity was gone
	- Essentially seconds after `get` was incl in mempoool, bot swept funds
- Apparently rescuing as an internal calll via authorized contract and passing variable from storage as `to` address did not protect
- Don't get sloppy
	- Use own node
	- Tweak contracts
	- Spend more time on scripts
- Don't rely on normal infra
	- Infura rejected tx because tx being submitted looked like it would fail
		- `set` and `get` would be in the same block
	- Using own node would solve this or knowing a miner
- MEV is a urgent problem that is being thought through and attempting to be tackled
	- Optimism has a vision
	- Starkware has a verifiable delay function called VeeDo







---
# References
https://www.paradigm.xyz/2020/08/ethereum-is-a-dark-forest
