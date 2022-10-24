202210240109
Status: 
Tags: #cypher

## Certora - Formal Verification

[[Bad Proofs in Formal Verification]]

Certora is a **pre-deployment** formal verification software that checks for bugs given invariants. When provided an invariant the software does a proof by induction to find counter examples where the invariant does not hold. If there are counter examples, then there exists a bug. If there are no counter examples, Certora spits out a proof proving that the invariant holds.

However, building proper specifications or rules is difficult. There are three components to a rule: precondition, operation, and postcondition. Poorly designed conditions can lead to undesired situations where a rule is created that does not test the intended scenario.

In the case of a vacuous rule, the precondition asserts a ridiculous claim like `0 > 1` that makes it so that there is no starting state. Therefore, the software can not come up with any counter examples given no starting state. In the case of a tautology, the postcondition asserts a condition that does not rely on the operation at all. These bad proofs create false positives that can lead to deployment of buggy code.

Certora tackles this by integrating automation for checking these scenarios. The vacuous rule can be detected by asserting something ridiculous as the postcondition and if it fails then it exists. Tautology can be detected by removing the pre condition and operation and if it passes then it exists.

**tl;dr** - It's better to be suspicious of proofs and take returned bugs seriously. Writing specifications is hard; however, automation and tools are being built to ensure good specs. Formal verifications require you to come up with invariants.

## Forta - Realtime Alerts & Monitoring

[[Hunting and Monitoring for On-chain Attacks]]

Forta is a **post-deployment** decentralized real-time alert and monitoring network that runs detection bots. The nodes provide confirmation that the bot that is deployed is being ran with provided parameters with no tampering by any party. A common belief is that hacks are atomic and once the block is confirmed there is no way to prevent it. However, in many hacks, Forta observed that hacks are often executed in stages across several blocks. The hacker typically follows these steps:

1. Funding through Tornado cash
2. Deployment of unverified contract on mainnet
3. Execution of flashloan through flashbots transaction
4. Exiting funds through Tornado cash

While this may not cover all of the hacks, it makes a statement that it is possible to detect a majority of hacks through a detection of patterns.

It is one thing for a bot to raise alerts on patterns but it is also important that there are as few false positives as possible. Given a bot with low precision, bot operators will find it difficult to consume and act upon alerts if there is a lot of noise. A potential solution is an aggregator of bots whose purpose is to filter out noise.

Forta provides pre-built detection kits for popular protocol types like DeFi, NFTs, and governance. Bot alerts can be configured with threat levels and alert message to provide control over what is emitted. We can design alerts around inconsistencies in the invariants of a particular protocol. For example, in a bridge protocol we should never see an inbalance in balances. In a NFT protocol, we should never mint an NFT with no actual funds to back it up. Critical alerts can consist of ACL changes, ownership transfers, and dangerous state changes.

Furthermore, an issue is that automatic responses based on alerts are not viable because there are false positives which could render your protocol unusable. Forta suggests that pausing a protocol is a surefire way to shut down the protocol and there could be other administrative options to solve. However this is seemingly not viable because given the time span of the attack, operators only have a little amount of time to decide on a course of action.

**tl;dr** - Hacks often follow a specific pattern. While bots do most of the heavy lifting, they are prone to false positives meaning it is the operator's responsibility to parse through the noise and act upon it (within less than a few blocks). The benefit of this system is while it does have its issues, it significantly reduces the timeline of the hack occuring to performing an incident response by providing realtime alerts. Reliance on one hack prevention system is not good enough, have redundancies to increase confidence. 







---
# References

