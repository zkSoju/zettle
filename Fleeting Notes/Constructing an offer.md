202206281843
Status: 
Tags: #seaport

# Constructing an offer
`FulfillBasicOrderTest.t.sol`
- Basic ETH to ERC721
```solidity
struct OfferItem {
    ItemType itemType;
    address token;
    uint256 identifierOrCriteria;
    uint256 startAmount;
    uint256 endAmount;
}
```

```solidity
struct ConsiderationItem {
    ItemType itemType;
    address token;
    uint256 identifierOrCriteria;
    uint256 startAmount;
    uint256 endAmount;
    address payable recipient;
}
```

```solidity
struct BasicOrderParameters {
    // calldata offset
    address considerationToken; // 0x24
    uint256 considerationIdentifier; // 0x44
    uint256 considerationAmount; // 0x64
    address payable offerer; // 0x84
    address zone; // 0xa4
    address offerToken; // 0xc4
    uint256 offerIdentifier; // 0xe4
    uint256 offerAmount; // 0x104
    BasicOrderType basicOrderType; // 0x124
    uint256 startTime; // 0x144
    uint256 endTime; // 0x164
    bytes32 zoneHash; // 0x184
    uint256 salt; // 0x1a4
    bytes32 offererConduitKey; // 0x1c4
    bytes32 fulfillerConduitKey; // 0x1e4
    uint256 totalOriginalAdditionalRecipients; // 0x204
    AdditionalRecipient[] additionalRecipients; // 0x224
    bytes signature; // 0x244
    // Total length, excluding dynamic array data: 0x264 (580)
}
```

- Fill `basicOrderParameters` by filling with fuzz parameters
	- Additional configuring for `zone`, `zoneHash`, `salt`, and `conduitKey` 
	- Ensure counter is the the current of the offerer
- Get hash of order of order and then sign with private key (happens offchain in production)
- Signature is stored in full as `bytes`
- Fulfill order with `basicOrderParameters` and supplying `paymentAmount` which is the amount to be paid

```solidity
        test721_1.mint(alice, context.args.tokenId);

        _configureOrderComponents(
            context.args.zone,
            context.args.zoneHash,
            context.args.salt,
            bytes32(0)
        );
        uint256 counter = context.consideration.getCounter(alice);
        baseOrderComponents.counter = counter;
        bytes32 orderHash = context.consideration.getOrderHash(
            baseOrderComponents
        );
        bytes memory signature = signOrder(
            context.consideration,
            alicePk,
            orderHash
        );

        basicOrderParameters.signature = signature;
        context.consideration.fulfillBasicOrder{
            value: context.args.paymentAmount
        }(basicOrderParameters);
        assertEq(address(this), test721_1.ownerOf(context.args.tokenId));
```

---
# References

https://github.com/L3NFT/seaport/blob/main/contracts/lib/ConsiderationStructs.sol
https://github.com/L3NFT/seaport/blob/main/contracts/lib/ConsiderationEnums.sol