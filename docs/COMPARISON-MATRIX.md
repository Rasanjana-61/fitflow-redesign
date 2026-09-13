# Technology Comparison Matrix

The matrix below records the baseline choices for the first release and the main alternatives considered. Scores are relative decision guidance, not benchmarks.

| Decision | Selected | Alternative | Why selected | Trade-off |
| --- | --- | --- | --- | --- |
| Frontend framework | React + TypeScript | Next.js | Simple client-first structure and fast iteration for the planned app | SSR and file-based routing would need to be added separately |
| Frontend tooling | Vite | Next.js tooling | Minimal build surface for a browser application | Less built-in full-stack convention |
| Backend framework | Fastify | Express | Strong performance, schema-friendly design, and a small core | Smaller ecosystem than Express |
| Backend language | TypeScript | Python | Shared types with the frontend and strong API tooling | Requires a separate Python runtime for AI work |
| AI service framework | FastAPI | Node.js AI endpoint | Python has the broadest model and evaluation ecosystem | Adds a second language and deployment unit |
| Primary database | PostgreSQL | MongoDB | Relational integrity fits users, plans, logs, and progress relationships | Schema changes require migrations |
| Cache and jobs | Redis | Database-backed jobs | Good fit for rate limits, transient state, and queues | Adds an operational dependency |
| API style | REST + OpenAPI | GraphQL | Straightforward service boundary and easy observability | Clients may make multiple requests for complex screens |
| Deployment packaging | Docker | Direct host installs | Consistent local, CI, and deployment environments | Requires container tooling |

## Decision Criteria

Choices prioritize maintainability, explicit service boundaries, validation of health-related data, local developer experience, and the ability to change AI providers without redesigning the product API.

These decisions are provisional until the first vertical slice validates the actual performance, hosting, and team constraints.