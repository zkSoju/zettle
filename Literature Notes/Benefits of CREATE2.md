202206071359
Status: 
Tags:

[[How does CREATE2 work]]
[[Comparing CREATE2 vs CREATE]]

When deploying contracts, `CREATE` already gives you the ability to know the address that the contract is being deployed to in advance with `address = hash(sender,nonce)`; however, it is not possible to park an address in advance. `CREATE2` uses the following calculation `address = hash(0xFF, sender, salt, bytecode)`. With `CREATE2` you can **park** or reserve an address in advance **regardless** of transactions sent in the meantime (which affect the nonce) used in `CREATE`. 
 
[[Counterfactuality with CREATE2]]

Initially the primary use case of CREATE2 was to avoid situations of counterfactuality where a user might be reliant on a non-deployed contract address to operate, but the threat or possibility of a third party deploying a contract to the same address is problemsome. 

[[Receiving funds without a wallet or being a part of the network]]

A greater use case for CREATE2 is to abstract away the burdens of key management and true self-custody, which slows down adoption and adds unnecessary anxiety to new users. Instead, user wallets can be represented as non-deployed contracts. This inherently provides two big benefits. When wallets are represented as contracts (similar to Starkware), there are additional freedoms to choose in a sense the desired level of "self-custody". A user could go the standard approach and manage their private keys in the same way you would an EOA/normal wallet, but the user also has the freedom to centralize key recovery (different from custodial wallets). The other benefit is that users could receive funds before even being a part of the network, similar to how you can receive funds to an email before registering with Zelle or PayPal.

[[Parking an identity contract]]







---
# References

