# SaaS Application

## Architecture Patterns
- Multi-tenant with tenant isolation (schema-per-tenant or row-level security)
- Frontend: SPA (React, Vue, Svelte) or SSR (Next.js, Nuxt, SvelteKit)
- Backend: API server (Node.js, Python, Go, Ruby)
- Database: PostgreSQL (recommended), MySQL, or managed DB
- Auth: OAuth2/OIDC, JWT sessions, or provider auth (Auth0, Clerk, Supabase Auth)
- Background jobs: Bull, Celery, Sidekiq, or cloud-native (SQS, Cloud Tasks)

## Key Decisions
- [ ] Tenant isolation strategy
- [ ] Auth provider vs self-hosted
- [ ] Billing provider (Stripe, Paddle, LemonSqueezy)
- [ ] Hosting (Vercel, Railway, Fly.io, AWS, GCP)
- [ ] Email provider (Resend, SendGrid, Postmark)
- [ ] File storage (S3, R2, Cloudinary)

## Standard Slices
1. Project scaffolding and configuration
2. Database schema and migrations
3. Authentication and authorization
4. Core domain models and CRUD
5. API routes and validation
6. Frontend pages and components
7. Billing integration
8. Email/notification system
9. Admin dashboard
10. Testing and CI/CD

## Testing Strategy
- Unit tests for business logic
- Integration tests for API endpoints
- E2E tests for critical user flows
- Auth flow testing

## Security Checklist
- Input validation on all endpoints
- Rate limiting on auth and public endpoints
- CORS configuration
- SQL injection prevention (parameterized queries)
- XSS prevention
- CSRF protection
- Secrets in environment variables only
- HTTPS everywhere
