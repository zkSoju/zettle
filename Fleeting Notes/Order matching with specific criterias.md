202205281615
Status: #fleeting
Tags: #seaport

# Order matching with specific criterias
```sol
function _matchAdvancedOrders(
	AdvancedOrder[] advancedOrders,
	CriteriaResolver[] memory criteriaResolvers,
	Fulfillment[] calldata fulfillments
) internal returns (Execution[] memory executions) {}
```

- `AdvancedOrder` contains general order details like signatures
- `CriteriaResolver` used for orders that have a specific criteria, uses the merkle proof
- `Fulfillment` specifies if it is an offer or a consideration (listing) and holds the order index or item index
- Functions collects items and orders and aggregates them if the recipients are the same
- All considerations must be zeroed out by opposing offer before token transfer occurs





---
# References
[[About Seaport]]
