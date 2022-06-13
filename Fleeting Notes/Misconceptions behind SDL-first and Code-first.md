202206101439
Status: 
Tags: #graphql

# Misconceptions behind SDL-first and Code-first
What is "schema first"?
	- Bad phrasing because making schema design a priority is important
		- Leads to better API design
		- Any shortcomings could result in a API that doesn't meet needs of business domain
	- **Drawbacks come from manually defining schema in SDL and resolvers afterwards instead of designing schema first**
- Code-first (aka. resolver first) is when GraphQL schema is implemented programmatically and SDL schema is generated artifact from that
	- **You still pay attention to upfront schema design**
[[Background of GraphQL server development]]








---
# References

https://www.prisma.io/blog/the-problems-of-schema-first-graphql-development-x1mn4cb0tyl3
