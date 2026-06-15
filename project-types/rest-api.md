# REST API

## Architecture Patterns
- Resource-oriented: URLs represent resources, HTTP methods represent actions
- Stateless: each request contains all needed context
- Layered: routes → controllers → services → repositories
- Consistent error responses with status codes
- Pagination, filtering, and sorting as first-class concerns

## Key Decisions
- [ ] Framework (Express, Fastify, Hono, FastAPI, Gin, Rails)
- [ ] Database and ORM/query builder
- [ ] Authentication (JWT, sessions, API keys, OAuth2)
- [ ] Validation library (Zod, Joi, Pydantic, Cerberus)
- [ ] Documentation (OpenAPI/Swagger)
- [ ] Rate limiting strategy

## Standard Slices
1. Project scaffolding and configuration
2. Database schema and migrations
3. Domain models and entities
4. Data access layer (repositories)
5. Business logic layer (services)
6. API routes and controllers
7. Request validation
8. Authentication and authorization middleware
9. Error handling middleware
10. Pagination, filtering, sorting
11. API documentation (OpenAPI spec)
12. Testing
13. Rate limiting and security headers

## URL Design
```
GET    /api/v1/resources          # List
POST   /api/v1/resources          # Create
GET    /api/v1/resources/:id      # Get one
PUT    /api/v1/resources/:id      # Replace
PATCH  /api/v1/resources/:id      # Partial update
DELETE /api/v1/resources/:id      # Delete
```

## Response Format
```json
{
  "data": {},
  "meta": {
    "page": 1,
    "per_page": 20,
    "total": 100
  }
}
```

## Error Format
```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input",
    "details": [
      { "field": "email", "message": "must be valid email" }
    ]
  }
}
```

## Testing Strategy
- Unit tests for services and business logic
- Integration tests for API endpoints (supertest, TestClient)
- Contract tests for response schemas
- Load tests for critical endpoints
