# Development Workflow

## Branching model

- `main` is kept clean for release-ready milestones.
- `dev` is the active integration branch for ongoing work until version `1.0.0`.
- Feature or experiment branches should target `dev`, not `main`.
- Pull requests into `main` should normally come from `dev`.

## Rationale

This keeps release history readable while preserving room for exploration and refactoring during early development.

## Practical guidance

- Treat `main` as the branch for tagged milestones and stable snapshots.
- Use `dev` for architecture work, experimentation, and integration.
- When a decision becomes stable enough to matter, capture it as an ADR.
- Revisit the workflow after `1.0.0` if the project grows or contributor traffic changes.
