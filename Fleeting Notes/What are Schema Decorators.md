202206101619
Status: 
Tags: #graphql

# What are Schema Decorators
- **Schema decorators** allow you to write
	- Schemas in SDL with no code resolve functions and custom logic
	- And also add functionality (validation/authorization) to specific parts of schema
	- Build reusable modules
		- Annotations to schema
		- Enforcing auth checks
		- Argument validation
		- Logging and profiling
		- Error handling
		- Connecting backend data stores
		- Filtering/sorting data
- We need schema decorators because as of now you have to
	- Create custom types and combine into schema
	- Write arbitrary code for resolvers
	- Add descriptions to types
- Currently lacking universal modular way to add features to schema







---
# References
https://www.apollographql.com/blog/backend/graphql-schema-decorators-3c01a445b628/
