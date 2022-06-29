202206281326
Status: 
Tags: #seaport

# Matching orders
- Contract matches a group of orders to a group of fulfillments (scan through each item)

--- 
The following happens for *each* item
1. Hash order 
2. Perform initial validation
3. Retrieve and update order status
4. Determine amount for each item
5. Apply criteria resolvers
6. Emit OrderFilled event
--- 
8. Apply fulfillments
9. Scan each consideration item and ensure none still have a nonzero amount remaining
10. Perform transfers as part of each execution







---
# References
https://github.com/L3NFT/seaport/blob/main/docs/SeaportDocumentation.md
