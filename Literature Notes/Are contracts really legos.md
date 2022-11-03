202211011232
Status: 
Tags:

## What are smart contracts?

[[What are smart contracts really]]

## How impactful is composability?

[[Composability is innovation]]

The beauty of smart contracts is it's permissionless and composable nature. It is the reason why DeFi protocols are often coined the term "DeFi legos", but beyond DeFi is composability really that impactful? What does it mean for the future of smart contract development? As it is right now, the biggest example of composability is the standardization of the ERC20 and other token standards. Yield aggregators are leveraging this by taking LP tokens, which represent shares of a pool, and route it through other opportunities to obtain the best yield for the end user. The ability to interact with a common interface in a permissionless way is like a superpower, it enables novel use cases that were not available before with proprietary and closed source software. This experience closely mirrors the creation of the TCP/IP protocol which was revolutionary and pushed innovation to another level. 

## Endless Adapters

[[Composability isn't possible without adapters]]

## Default Framework

[[What is the Default Protocol Framework]]

Interoperating and composing with other contracts is not as feasible as many might think. In the current state of smart contracts, security is a major concern. Protocols are becoming increasingly more complex making it difficult to not only interface with other protocols, but also audit. Upgradeability, intricate logic, non-standardized interfaces, and coinflip audits leads to the feeling that integrating with other protocols is not worth the risk or the effort. Currently, heavy documentation is a necessity for understanding, but Default aims to solve that. Architecting a protocol in the way Default describes is not only beneficial for auditors but also developers attempting to contribute to the codebase. You can think of the Default framework as a microservices architecture for smart contracts. Module smart contracts are siloed and manage the backend data models. Policy smart contracts act as the frontend or middleman for interacting with modules. This becomes much simpler to understand because the core state and data management operations of the application lives within the modules abstracted away from the users. As a result, policies contain only business logic, so it becomes easy to understand how it works without needing to know the intricacies of the underlying data operations. 




 




---
# References

