202206141613
Status: 
Tags:

# Setting up NestJS & Prisma with AWS Lambda
1. Create NestJS app skeleton with `nest new`
2. Set `DATABASE_URL` env variable
3. Add schema to `schema.prisma`
4. Create RDS and make publicly accessible
5. Run `npx migrate` which creates SQL files and runs them against DB from `schema.prisma`
6. `npm install @prisma/client` which is a type-safe database client generated from Prisma model definitions
	1. Able to expose CRUD operations tailored to models
7. Make sure to run `prisma generate` every time you make a Prisma model change to update generated client
8. Abstract away Prisma Client API in a service `prisma.service.ts`
9. Create a `user.service.ts` to handle CRUD operations to user schema
	1. Notice Prisma client types ensure methods exposed are properly typed saving boilerplate code
	2. All services will take in `PrismaService` into the constructor and use its API to query and mutate (acts as a wrapper class)
10. Prisma interferes with NestJS `enableShutdownHooks` ...
11. Install GraphQL + Typescript support `npm i @nestjs/graphql @nestjs/apollo graphql apollo-server-express`
12. Use `npm install --save-dev prisma-nestjs-graphql` to generate models for code-first approach from Prisma models (can customize for validation?)
	1. `npm install graphql-type-json prisma-graphql-type-decimal` If you need `JSON` or `decimal` type



Prisma is basically used to instantiate database with types defined in prisma model and create type safety for usage with NestJS services

- Make sure to configure tsconfig to include graphql files in webpack so that GraphQLModule from NestJS can see it and generate typings
- Make sure to check VPC if postgres is connecting through PgAdmin but not AWS





---
# References

https://docs.nestjs.com/recipes/prisma
https://github.com/vendia/serverless-express/tree/mainline/examples/basic-starter-nestjs
https://github.com/unlight/prisma-nestjs-graphql