202206101527
Status: 
Tags: #graphql

# Problems with SDL-first
- Inconsistencies b/w definition and resolvers
	- **Schema has to be synced with resolvers at all times!**
	- `graphqlgen` and `graphql-code-generator` was built to help keep these in sync
- Modularization of graphQL schema
	- When writing large schemas you want to split them up into smaller parts
		- ex. features or products
	- `graphql-import` and `graphql-modules` built for imports and schema separation
- Redundancy in schema 
	- Repeated code in SDL definitions
	- Relay-style connections (powerful pagination spec)
		- Lots of boilerplate/repeated code to implement
	- No generic solutions
- IDE support 
	- SDL represented as plain strings so tooling doesn't recognize structure
	- How do you leverage GraphQL types in editor work flows?
		- Auto-completion, build-time errors
- Composing GraphQL schemas
	- How do you compose a number of existing (distributed) schemas into one?
	- `graphql-tools` provides schema stitching and schema delegation for more control of composition
- **Summary** - SDL-first can work, but requires too many tools

- AppSync provides tooling for SDL-first where resolversers are auto generated from schemas
- Risk of ecosystem lock-in from each toolchain







---
# References

