---
name: "architecture-guidelines"
description: "Python architecture guidelines for the team — layered architecture, repository pattern, configuration, and dependency injection. Load when reviewing a diff for architecture decisions."
---

- **Layered architecture** — Business logic lives in a service module. Entrypoints (route
  handlers, CLI commands, a script's `main()`) parse input and format output only; they
  contain no business logic and perform no data access directly.
- **Repository pattern** — Services obtain data through a `Repository` only. A service that
  calls an API client, HTTP client, or database/ORM directly bypasses the repository layer.
- **Configuration** — Configuration and secrets are loaded from environment variables or a
  single config module, never hardcoded or read ad hoc in multiple places.
- **Dependency injection** — Dependencies are passed via constructor or parameters. A
  module-level global singleton or a ServiceLocator pattern is not allowed.

When citing a violation, name the guideline (for example "violates the Repository pattern").
The canonical decision records live in `docs/adr/`.
