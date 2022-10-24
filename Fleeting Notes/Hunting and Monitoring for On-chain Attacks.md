202210240131
Status: 
Tags: #cypher #security 

- Popular belief is that attacks are atomic meaning that once the block is mined then there is nothing that can be done
- However attacks are typically executed in stages
	- Funding via tornado cash
	- Preparation through suspicious contract deployment
	- Exploitation through a flashloan in conjunction with a flashbot tx to bypass the mempool
	- Money laundering through tornado cash
- Example
	- Inverse Finance - collateralized lending protocol
		- Funding was received by hacker through tornado cash
		- Hacker flashloaned on Aave through flashbots, so mempool was bypassed
		- Blocksec explorer shows the balance changes where large amounts of tokens were received by hacker and extracteed from which contracts
		- Used tornado cash to exit funds
		- Entire process took 8 minutes
		- Manual incident response not sufficient but automatic could be
- Comprehensive security strategy
	- Pre-deployment
		- Template contracts
		- Audit
		- Formal verification
	- Post-deployment
		- Bug bounties
		- Real time monitoring/alerting (this is where Forta steps in)
		- Incident/emergency response
- Forta is a security and alarm system
	- Decentralized network that monitors on chain activity
	- **Scan node** runs bots against each block 
	- **Detection bots** are scripts written and published by developers to Forta network
	- Forta explorer shows deployed bots on network and real time alerts that are raised
	- How are bots compared?
		- Precision
			- Of the alerts being raise what percentage are false positives
		- Recall
			- Of the alerts being raised what percentage are true positives
	- Potential solution
		- Aggregator of noisy bots to extract true positives
	- Issue is that automatic responses are not viable because there are false positives which could render your protocol unusable 
	- Pausing a protocol is a surefire way to shut down the protocol but there could be other administrative options to solve
		- However this is still not viable because given the time span of the attack, operators only have a little amount of time to decide on a course of action
	- Pre-built threat detection kits available for types of protocols
		- DeFi
		- NFTs
		- Governance
	- Typical protocol alerts
		- We want to build a bot that finds inconsistencies in protocol invariants (things that must hold true)
			- Examples
				- Bridge balance difference
				- Issuing of tokens with no actual backup
				- Minting NFTs with no actual backup
				- Unexpected fund transfers
		- How can we classify alerts
			- Critical
				- Events that should not happen silently
					- Huge withdraws
					- Huge balance changes
				- Events that should never happen
					- Ownership to EOA/null address
					- Self-destruct contract
					- Changes  in immutable slots
				- ACL changes (roles)
			- Repetitive events (events we expect to see but could bring up issues when there is variance)
				- Oracle reports
				- Rewards distribution
				- Stake deposits
				- Validator keys upload






---
# References

https://www.youtube.com/watch?v=G4esm_AQOOc