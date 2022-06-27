202206141801
Status: 
Tags:

# NestJS GraphQL Resolvers (Code-first)
- You can constructor a resolver from multiple providers (ex. `PostsService` and `AuthorsService`)
- Think of a service as an exposed Prisma API to the database
- When defining a **field resolver** a resolver for a property of the parent class we **must** indicate the parent type in the `@Resolver` decorator
	- Populating a field of a parent with a call to another service (ex. using the `id` of the parent)
- Multiple queries will be **aggregated** into a single query type in the generated SDL
- If doing code-first, use plugin to generate input/arg types then modify NestJS generated resolvers/services to match






---
# References
https://docs.nestjs.com/graphql/resolvers
