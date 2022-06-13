202206101544
Status: 
Tags:

# Approaches with NestJS
- Ability to choose either code-first or schema-first
- - `autoSchemaFile` property to generate to location or on the fly in memory
- Types in generated schema will be in order defined, set `sortSchema` if you wish
- In the **code first** approach, you use decorators and TypeScript classes to generate the corresponding GraphQL schema.
	- We don't create SDL schema by hand
	- Typescript decorators from class annotations are used to generate
- Typically we would write
```graphql
type Author {
  id: Int!
  firstName: String
  lastName: String
  posts: [Post!]!
}
```
- With TS decorators to annotate fields of classes
```typescript
@ObjectType()
export class Author {
  @Field(type => Int)
  id: number;

  @Field({ nullable: true })
  firstName?: string;

  @Field({ nullable: true })
  lastName?: string;

  @Field(type => [Post])
  posts: Post[];
}
```
- NestJS generates the SDL schema from the code above






---
# References
https://docs.nestjs.com/graphql/quick-start#code-first
https://docs.nestjs.com/graphql/resolvers