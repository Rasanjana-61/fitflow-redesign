# FitFlow Redesign

FitFlow is a fitness planning platform for creating personalized workout and nutrition plans, tracking progress, and getting AI-assisted coaching. This repository is organized as a modular application with a frontend, a core backend, and a dedicated AI service.

## Repository Structure

```text
fitflow-redesign/
|- frontend/    Web application and user experience
|- backend/     Authentication, plans, tracking, and API
|- ai-service/  Recommendations and coaching workflows
|- docs/        Architecture and technology decisions
```

## Documentation

- [Tech stack summary](docs/TECH-STACK.md)
- [Technology comparison matrix](docs/COMPARISON-MATRIX.md)
- [Architecture and system diagram](docs/ARCHITECTURE.md)

## Planned Product Areas

- Account and profile management
- Fitness goals, workout plans, and progress tracking
- Nutrition planning and habit tracking
- AI-assisted recommendations with user-controlled inputs
- A responsive experience for desktop and mobile browsers

## Local Development

The project is currently in the documentation and foundation phase. The service folders are reserved for their respective applications; implementation-specific setup commands will be added as each service is initialized.

Before contributing, review the architecture and comparison documents so new dependencies and service boundaries remain consistent.

## Principles

- Keep core product rules in the backend rather than duplicating them in clients.
- Keep AI capabilities behind a dedicated service boundary.
- Treat user health data as sensitive and minimize data shared with external providers.
- Prefer observable, testable workflows over implicit cross-service behavior.