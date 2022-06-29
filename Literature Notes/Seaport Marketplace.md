202206021457
Status: #fleeting
Tags:

# Seaport Marketplace

[[About Seaport]]

Repository is composed of both Foundry and Hardhat testing frameworks for increased coverage through different testing methodology. Seaport utilizes offchain listings and composite order matching through [[Improved off-chain message signing]] in order to achieve low gas usage.

[[Seaport Terminology]]

[[Creating an order]]

A typical order is composed of two primary parts: an **offer** and a **consideration**. The wordage may be confusing at first, but think of the offer as the item(s) being offered and the consideration as the item(s) expected to be received.

![[Screen Shot 2022-06-08 at 8.53.41 AM.png]]

Key features:
- Supports a wide range of token types: native token, ERC20, ERC721, ERC1155 
- Differing amounts and times can be specified to calculate listing price linearly with time
- Additional `recipient` component can be supplied to consideration to support "tipping" (relayer and referrals)
- `zone` account can be provided to essentially create "private" sales between offerer
- User can opt to trust the primary Seaport contract for token approvals and transfers or supply a `conduitKey` that references a conduit contract that will transfer instead 

There are two order preferences for `orderType` and an order can only be one of the four states: 
- Partial fulfillment support
	- `FULL` means that fulfillment must be in full
	- `PARTIAL` means that fulfillment can be satisfied by a fraction (amount must be cleanly divisible) of amount
- Authorization
	- `OPEN` indicates anyone can execute the order
	- `RESTRICTED` indicates only the offerer or the zone can execute the order

An an order can be fulfilled in three ways:
- **Personal fulfillment** - fulfill as `msg.sender`
- **Signature based fulfillment** - approve using signature
- **Onchain fulfillment** - validating on-chain order

[[Matching orders]]

[[Fulfilling orders]]





---
# References

