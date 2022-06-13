202206101405
Status: 
Tags: #graphql

# Backend architecture for a GraphQL endpoint
![[Pasted image 20220610140614.png]]
- ApolloClient -> NestJS 
- When building GraphQL API against a database
	- Apollo server needs to send database queries inside of GraphQL resolver, only receives GraphQL query/mutation
		- Prisma is used inside of these resolvers to map these queries and read/white to their respective database (allows for flexibility to choose any DB)
- Prisma uses prisma schemas to define database schemas and model relations
- Prisma is compatible with
	- Apollo Server (SDL first)
		-  [[Schema definition language (SDL) first design in Apollo]]
	- Nexus (Code first)
		- [[Code first approach with Nexus and TypeGraphQL]]
	- TypeGraphQL (Code first)
- [[Misconceptions behind SDL-first and Code-first]]





---
# References
https://www.prisma.io/apollo
