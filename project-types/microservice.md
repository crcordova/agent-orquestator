# Microservice

## Architecture Patterns
- Single responsibility: one service owns one domain capability
- API-first: define contracts before implementation
- Independent deployability
- Own data store per service (no shared databases)
- Communication: synchronous (REST/gRPC) or asynchronous (message queue)
- Service discovery and health checks

## Key Decisions
- [ ] Communication protocol (REST, gRPC, GraphQL, message queue)
- [ ] Data store (SQL, NoSQL, event store)
- [ ] Service mesh or direct communication
- [ ] Container orchestration (Docker Compose, Kubernetes)
- [ ] API gateway (Kong, Traefik, AWS API Gateway)
- [ ] Observability stack (logging, metrics, tracing)

## Standard Slices
1. Service scaffolding and configuration
2. Domain model and data schema
3. API contract definition (OpenAPI/Protobuf)
4. Core business logic
5. Data access layer
6. Integration with other services
7. Health checks and readiness probes
8. Error handling and retry logic
9. Observability (logging, metrics, tracing)
10. Container configuration (Dockerfile, docker-compose)
11. CI/CD pipeline
12. Testing (unit, integration, contract)

## Testing Strategy
- Unit tests for business logic
- Contract tests for API boundaries (Pact, Dredd)
- Integration tests with test containers
- Load tests for performance-critical paths

## Inter-Service Communication

### Synchronous
- REST: simple, universal, higher latency
- gRPC: fast, typed, requires protobuf

### Asynchronous
- Message queue: RabbitMQ, NATS, Kafka
- Event-driven: publish domain events
- Saga pattern for distributed transactions

## Observability
- Structured logging (JSON format)
- Metrics (Prometheus, OpenTelemetry)
- Distributed tracing (Jaeger, Zipkin)
- Health endpoints: `/health` and `/ready`
