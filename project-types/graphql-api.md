# GraphQL API

## Architecture Patterns
- Schema-first or code-first approach
- Resolver-based architecture
- Data_loader for N+1 prevention
- Subscription support for real-time
- Federation for distributed graphs

## Key Decisions
- [ ] Approach: schema-first vs code-first
- [ ] Framework (Apollo Server, GraphQL Yoga, Hasura, Strawberry, Sangria)
- [ ] Database and data access pattern
- [ ] Authentication in resolvers
- [ ] Complexity limits and depth limiting
- [ ] Caching strategy ( persisted queries, CDN)

## Standard Slices
1. Schema definition (types, queries, mutations, subscriptions)
2. Project scaffolding and server setup
3. Database schema and models
4. Data sources and loaders
5. Resolver implementation
6. Authentication and authorization
7. Input validation
8. Error handling
9. Subscription setup (if needed)
10. Testing
11. Documentation and playground

## Schema Design
```graphql
type Query {
  users(filter: UserFilter, pagination: PaginationInput): UserConnection!
  user(id: ID!): User
}

type Mutation {
  createUser(input: CreateUserInput!): CreateUserPayload!
  updateUser(id: ID!, input: UpdateUserInput!): UpdateUserPayload!
  deleteUser(id: ID!): DeletePayload!
}

type User {
  id: ID!
  email: String!
  name: String!
  posts(first: Int, after: String): PostConnection!
}
```

## Testing Strategy
- Unit tests for resolvers
- Integration tests with test client
- Schema validation tests
- Performance tests for complex queries
- Depth and complexity limit tests
