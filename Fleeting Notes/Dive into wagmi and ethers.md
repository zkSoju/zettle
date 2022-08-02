202207080228
Status: 
Tags: #wagmi #ethers

# Dive into wagmi
- If provider is a function or takes in a chainId and returns a provider then store the provider of the current chainId, else just store the provider
- `typeof provider === 'function' ? provider({chainId}) : provider`
- Check for autoConnect flag and then try to get current chainId
- If provider is alchemy or infura then you can't call getSigner, you need to use `window.ethereum`







---
# References
https://github.com/tmm/wagmi/blob/main/packages/core/src/client.ts
