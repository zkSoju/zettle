202205281707
Status: #fleeting
Tags: #seaport

# Creating an order

- `offerer` supplies offered items and must:
	- fulfill order personally (`msg.sender == offerer`)
	- approve the order through signature (65 byte ECDSA, 64 byte EIP-2098, `isValidSignatureCheck`)
	- listing order on-chain via `validate`
- `zone` is an optional secondary account that can also `cancel` orders and can create "Restricted" orders that can only be executed by the zone or offerer
---
- `offer` contains array of items that may be transferred from offerer's account
	- `itemType` as native token (ex. Ether), ERC20, ERC721, ERC1155, ERC721 w/ criteria or ERC1155 w/ criteria
	- `token` is token address
	- `identifierOrCriteria` can be provided to provide token identifier or a merkle root composed of valid set of token identifiers (ex.token ID) 
	- `startAmount` represents amount of item in question required for order to be fulfilled
	- `endAmount` if difference than start amount, realized amount is calculated linearly since order becomes active
- `consideration` contains array of items to be received to fulfill order and contains same components as `offer` with the additional 
	- `recipient` component to support "tipping"
---
- `orderType` indicates one of four types (two preferences)
	- `FULL` indicates order does not support partial fills
	- `PARTIAL` enables partial/fractional fulfillment with the requirement that each item must be cleanly divisible
	- `OPEN` call to execute order can be called by any account
	- `RESTRICTED` only offerer or zone can execute order
- `startTime` 
- `endTime` used with `startTime` to determine current amount when `startAmount` is different from `endAmount`
- `zoneHash` 32 byte value provided to zone to utilize in order to determine authorization of order
- `salt` arbitrary source of entropy
- `conduitKey` 32 byte value that indicates which conduit from `conduitController` [[Permissioned controller used for upgradeability]] should be used, if zero hash then offerer will grant Seaport approval
- `nonce` nonce of given orfferer






---
# References
https://github.com/ProjectOpenSea/seaport/blob/main/docs/SeaportDocumentation.md#sequence-of-events
