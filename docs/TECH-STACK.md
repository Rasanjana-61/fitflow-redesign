# Tech Stack Summary

This is the proposed baseline for the first implementation. It favors a productive TypeScript stack while keeping the AI runtime independent so model and library choices can evolve without coupling the core API to Python.

| Area | Proposed technology | Purpose |
| --- | --- | --- |
| Frontend | React + TypeScript + Vite | Fast, type-safe web application development |
| UI styling | CSS Modules or a small shared design system | Local styles with reusable UI primitives |
| Client data | TanStack Query | Server-state fetching, caching, and request states |
| Backend API | Node.js + TypeScript + Fastify | Lightweight, typed HTTP API |
| API contract | OpenAPI | Shared contract for clients and service integrations |
| Validation | Zod | Runtime validation at API and service boundaries |
| Primary data store | PostgreSQL | Users, plans, activity, nutrition, and progress data |
| Caching and jobs | Redis | Short-lived cache, rate limits, and background job coordination |
| AI service | Python + FastAPI | Model orchestration and recommendation workflows |
| AI integration | Provider adapter with structured JSON output | Allows model providers to be swapped and responses validated |
| Testing | Vitest, Playwright, and pytest | Unit, browser, and AI-service testing |
| Delivery | Docker + CI pipeline | Reproducible local and deployment environments |

## Boundary Rules

- The frontend communicates with the backend API; it does not access PostgreSQL or model providers directly.
- The backend owns authorization, user data, product rules, and persistence.
- The AI service receives the minimum context needed for a recommendation and returns a validated result.
- AI output is advisory. Backend validation and product rules remain authoritative.

## Initial Non-Goals

- Training or hosting a foundation model in this repository
- Direct device integrations before the core tracking workflow is stable
- A microservice for every domain area