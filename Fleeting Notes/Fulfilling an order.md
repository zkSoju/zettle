202206080935
Status: 
Tags: #seaport 

# Fulfilling an order
[[Usage of fulfillment functions]]


- General overview
	- Orders require preapproval of marketplace contract or corresponding conduit specified by the key
	- **Fullfill order or advanced order**
		- **Normal Order**
			- Does not support partial filling or criteria based
			- Though filling remainder of partially filled order is supported
			- How it works
				1. Casts order to an "advanced" order using `OrderFulfiller` library
					1. ![[Pasted image 20220608143123.png|400]]
				2. Validate order that includes conduit if provided and 0 criteria resolvers
					1. Standard reentrancy prevention `OrderFulfiller`
					2. Ensure current time falls within order's valid timespan using library `Verifier`
						1. If invalid time and no reverts, return zeroed values 
					3. Ensure validity of fraction provided (in this case 1/1)  `OrderValidator`
					4. Ensure order type supports partial fill if fraction other than 1/1 provided `OrderValidator`
					5. Assert valid considerations then derive order hash  `Assertions`
						1. Ensure considerations provided is at least number of original `ConsiderationStructs`
						2. Derive order hash from current nonce and order parameters
							1. Current autoincrementing nonce stored for each address `NonceManager`
							2. Uses EIP-712 [[Improved off-chain message signing]] which defines structured data signing with `domain`, `types`, `data`
							3. Order hash is computed as `keccak256(abi.encode(types,data))`
							4. This example uses 3 types: `Offer`,`Consideration`,`Order`
					6. Assert restricted order have valid submitter or pass zone check
						1. ...
					7. Check order status to make it's fillable and it's not cancelled `Verifier`
						1. If invalid time and no reverts, return zeroed values 
					8. Verify signature of digest (domain separator + hash) is offerer
						1. Skip if caller is offerer (which )
					9. If order has non-zero denominator it is partially filled
						1. ...
					10. Return hash and fraction to fulfill
				3. Apply criteria resolvers (none in this case)
				4. Apply fractions and transfer assets
	- **Fulfill basic order**
		- Similar to above specification only caveat is that the offer must contain a single offer item (could be greater amount if not ERC721)







---
# References
https://github.com/ProjectOpenSea/seaport/blob/main/docs/SeaportDocumentation.md
