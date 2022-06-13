202205281631
Status: #fleeting
Tags: #seaport #amm

# Aggregation of fulfillments
```sol
function _applyFullfillment(
	AdvancedOrder[] memory advancedOrders,
	FulfillmentComponent[] calldata offerComponents,
	FulfillmentComponent[] calldata considerationComponents
) internal view returns (Execution memory execution) {}
```

This is used for efficient order matching. 

An example would be where there are two orders
1 Moonbird NFT -> 10 ETH and 50 DAI







---
# References
[[About Seaport]]