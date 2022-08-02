202206292345
Status: 
Tags: #seaport #real3

# Seaport Migration
- BaseOrderComponents are used for order hashing and signing (offerer)
- BasicOrderParameters is used in final `fulfill` function
- OrderComponents are a subset of OrderParameters
	- OrderParameters breaks down each Offer and Consideration

- Store OrderComponents inside of schema and then construct order parameters based on components


```solidity
struct OrderComponents {
    address offerer;
    address zone;
    OfferItem[] offer;
    ConsiderationItem[] consideration;
    OrderType orderType;
    uint256 startTime;
    uint256 endTime;
    bytes32 zoneHash;
    uint256 salt;
    bytes32 conduitKey;
    uint256 counter;
}
```

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



---
# References

