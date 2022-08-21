202208091142
Status: 
Tags: #mev

# MEV Strategy for Synthetix
- KALEB alpha leaker posted a potential opp in Synthetix contracts
- Scoping the opp
	- Synthetix trailed using ETH as collateral to mint sUSD and sETH
	- Voted for trial to end, but there were millions in outstanding loans so they made any position liquidate-able
		- This would be triggered by the pDAO address on public mempool
	- sUSD or sETH would need to be returned to receive ETH collateral + more for incentive
	- Backrun pDAO tx to take advantage
- Follows the liqudations [[Lending protocols liquidations introduce a MEV opportunity]] strategy
- Understanding the opp
	- `setLoanLiquidationOpen()` which is only callable by `pDAO` the owner, allows for liquidation of unclosed loans
	- `liquidateUnclosedLoan()` takes loan ID, address, and liquidates loan
		- Usable by anyone after liquidation is opened 
	- Now find which loans to liquidate and how much sETH/sUSD needed
	- `openLoanIDsByAccount()` gets IDs of open loans associated w/ account
	- `getLoanInformation()` returns data about loan given ID and owner
	- Problems
		- Contracts don't tell which addresses have outstanding loans
			- Solution: Download all tx associated with contracts on Etherscan and use excel to create list of unique accounts
			- Use getLoans to find out if address had outstanding loans
			- Use getLoanInformation to get collateral amount, sUSD/sETH issued, and interest
			- Sort by loan amount and save as json
		- Uncertain how much collateral received from liquidated a loan
			- **Calculation could be done onchain, but would be gas inefficient which ruins chances to compete with others**
			- Used scripts with a custom smart contract to quickly extract a batch of loan information and bring off-chain for calculation
- Construct execution contract
	- Option 1: Flashloan ETH -> USDC -> sUSD -> Liquidate sUSD -> Receive ETH -> Payback ETH
	- Option 2: Flashloan sUSD -> Liquidate sUSD loan -> receive ETH -> USDC -> sUSD -> Payback sUSD
	- Ultimately chose dYdX to flashloan ETH because there was no fee
	- sUSD was only available on AAVE
	- Strategies taken to minimize gas usage
		- Performed many liquidations in one tx which reduces fixed gas costs
		- Opted for exactOutput to avoid `balanceOf` call in order to ETH -> USDC -> sUSD on Uni V3
		- Tradeoff of precision for gas efficiency
			- But all okay if flashloan was paid off
		- Approvals were made in constructor to pay at time of deployment and save usage at execution time
		- *Look into gas tokens*
		- Functions named such that selectors had leading 0s
- However, large loans began to return money so opp was not very large
- Plan execution
	- Flashbots MEV Geth runs auction where highest gas price 
		- [[Understanding bundle pricing with Flashbots]]
	- Maximize gas price of bundle **not total ETH paid** which means gas fee determined by network traffic is not included
	- According to tests, only top 4 sUSD loans were the most gas efficient
		- sETH loans were significantly smaller making them less gas efficient
	- Essentially you want to maximize gas costs and capture the most MEV
		- As you liquidate more loans, you make less profit and pay more gas
- Flashbots auction and bundle ordering
	- Each bundle dependent on tx from pDAO making loans lilquidate-able
	- Bundle will fail if pDAO tx not included
	- If pDAO tx included in all, only one will succeed
	- Leveraging nuance of Flashbots auction
		- Bundles simulated to derive gas price and check failures
		- Bundles ordered according to gas price then resimulated to find conflicting bundles and ensure no bundle gas price is lower than expected
			- Tackles case where searchers tried to game auction by lowering miner payment post bundle merge which is normally not possible (?)
	- Instead of underpaying, you could overpay in second round of simulation
		- Submit first bundle with pDAO tx 
		- Create additional check for remaining bundles
			- Bundles would infer which "round" of simulation they were in and change execution
				- Fail if "first" because they would fail if tried
				- When in "second", bundles would be simulated *behind the bundle* with pDAO tx and succeed
				- These extra checks cause for a *higher* gas price causing no issue with the two round auction rules
- Execution
	- Blocknative used to monitor pDAO account and streamed to bot
	- Two monitoring scripts ran to pull data, derive optimal bundle strategy, and produce data used in contract
		- Saved results locally
	- Execution script receive pending tx, load bundle strategy output, craft bundles, and send to Flashbots
- Moment of truth
	- Someone tried baiting bot by sending a tx to relevant tx
	- No flashbots blocks were mined so mempool bot sniped all profitable loans
		- Widespread adoption of Flashbots, quite unlucky there was streak of non-Flashbots blocks







---
# References
https://blog.synthetix.io/deprecating-ethercollateral-loan-contracts/
https://bertcmiller.com/2021/09/05/mev-synthetix.html