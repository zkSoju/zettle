202210311512
Status: 
Tags: #security #zkrollup 

- Traditional usage of cryptography was for internet based applications, **secure communication**
	- How do we securely send credit card data to Amazon without being intercepted or changed?
	- Encryption and key exchange
- Now we can use cryptography for blockchain systems to ensure **data integrity**
	- Use case isn't to hide information but rather ensure integrity
	- Signatures, commitments, ZK proofs
---
- SNARK - succinct proof that a certain statement is true
	- "short" and "fast" to verify
- zkSNARK - proof is reveals nothing about m
- [[ZK Proofs]]
- ZK and cryptography which was considered before as pure theory is now being deployed and actively worked on as proof systems by billion $ companies
- Written 30 years ago, "In this setup, a slow expensive computer can monitor the operation of a herd of GPUs working with unreliable software" (with zk proofs?)
- This usage was not popularized because devices were becoming increasingly less expensive and more powerful
- Until the blockchain came along and can be describe as exactly that, a slow expensive computer
---
- Some applications like zkRollups and zkBridges don't actually use zk property of zkSNARKs, just the succint and easy to verify properties
- Some applications are non blockchain related
	- C2PA standard for cameras to provide a signature for location and timestamp of a photo
		- Fights against fakes and disinformation
	- Issue
		- Media outlets do post-processing like cropping, resizing, and greyscaling which makes so that computers can't verify sig anymore
	- Suggested solution
		- Editting software signs
		- Issue with this is untrusted software embedding keys
	- Solution
		- zkSNARKs prove signer knew original image, operations of edits, and signature
- Improvements to provers have made proof generation relatively fast (0-60s) and proof verification very fast (~2ms)
- What does the future hold?
	- Potential market for anyone with a GPU to get paid to create proofs
	- This increases availability for provers and pushes innovation in space






---
# References
https://www.youtube.com/watch?v=kCqrd1MQ1no&list=PLS01nW3Rtgop6VBy4Dvhea-hzOR2FAqsy&index=2
