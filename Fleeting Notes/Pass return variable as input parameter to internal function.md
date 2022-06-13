202205281651
Status: #fleeting
Tags: #seaport #gasoptimizations

# Pass return variable as input parameter to internal function

```sol

function _applyFulfillment(...) returns(Execution memory execution){
	_aggregateValidFulfillmentOfferItems(
		advancedOrders,
		offerComponents
		execution
	)
}

function _aggregateValidFullfillmentOfferItems(
	AdvancedOrders[] memory advancedOrders,
	FulfillmentComponent[] memory offerComponents,
	Execution memory execution
)
```

- Saves a small amount of gas versus constructing a new Execution in memory in the `_aggregateValidFullfillmentOfferItems` function and then returning it






---
# References
[[About Seaport]]
[[Aggregation of fulfillments]]