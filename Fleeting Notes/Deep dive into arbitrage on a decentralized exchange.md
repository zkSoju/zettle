202208012034
Status: 
Tags: #dex #mev

# Deep dive into arbitrage on a decentralized exchange
- Price differences between exchanges that operate on similar systems that where some rely on directly on order history are inevitable
	- These transactions are processed sequentially 
- Smart contract enabled trade atomicity
	- We can build bots that use proxy contracts (multicall?) to execute several orders in a single transaction 
		- Transactions themselves are atomically batch process
		- Which reverts if any trade fails
	- As a result, arb have opportunity to create single tx composed of multiple trades with the all or nothing model
	- In a traditional arb, trades are probabilitistic meaning that there is a chance one of the two transactions fail
	- A smart contract proxy enables guaranteed all or nothing profits
	- [[An example of pure revenue]]





---
# References

