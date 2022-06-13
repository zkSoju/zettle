202206101447
Status: 
Tags: #graphql

# Background of GraphQL server development

- Background 
	- Phase 1: `graphql-js` was used to build server with schema defined as plain JS object
		- ![[Pasted image 20220610144131.png|200]]
		- Too verbose compared to SDL now
		- ![[Pasted image 20220610144033.png|200]]
	- Phase 2: `graphql-tools` popularized schema-first
		- Separated schema definition from actual implementation
			1. Write GraphQL schema definition in SDL
			2. Implement required resolver functions
		- SDL first benefits
			- Readability
			- Quick building
			- Schema design is not afterthought
			- Definition can be used as API documentation
			- Communication tool b/w frontend-backend
	- Phase 3: Developing new tools to tackle scalability issues with SDl-first
		- Many problems arise that are solveable individually
			- Issue is each problem requires learning/using new tools
				- Excessive overhead slows developers down

[[Problems with SDL-first]]






---
# References
https://relay.dev/graphql/connections.htm