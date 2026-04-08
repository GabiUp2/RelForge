# ADR-0007: Evaluate Nix for reproducible development environments

- **Status:** proposed
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** tooling, nix, reproducibility, developer-experience
- **Origin:** development environment discussion
- **Related:** ADR-0002, ADR-0004

## Context

The project is expected to be developed across multiple machines and environments. That increases the risk of dependency drift, inconsistent tooling versions, and local setup friction.

Because RelForge is intended to mix Python orchestration with selected lower-level modules, the environment may eventually need to support:

- Python and project-specific Python dependencies,
- Zig toolchain and related development tools,
- test tooling,
- formatting and linting tools,
- and possibly database client libraries or other native dependencies.

We want to reduce machine-specific setup pain and improve reproducibility for both local development and future collaboration.

## Decision

We will explicitly explore **Nix** as a candidate solution for reproducible development environments.

This is currently an evaluation item, not a final commitment.

## Alternatives considered

### Ad hoc per-machine setup
Pros:
- low upfront effort
- familiar

Cons:
- dependency drift
- harder onboarding
- fragile reproducibility

### Python virtual environments plus manual system setup
Pros:
- simple for Python-only work

Cons:
- weak coverage for non-Python tooling
- system dependencies remain inconsistent

### Nix-based development environment
Pros:
- strong reproducibility potential
- cross-machine consistency
- good fit for polyglot tooling

Cons:
- learning curve
- extra tooling complexity
- may be more than needed at very early stages

## Consequences

### Positive
- The project keeps reproducibility as an explicit design concern.
- Future setup work can be guided by a clear question instead of being improvised repeatedly.

### Negative
- Adds one more architectural/tooling question to evaluate.

### Follow-up
- Determine whether Nix should cover only development shells or also builds and CI.
- Compare Nix against lighter alternatives for the early project stage.
- Revisit this ADR once practical experimentation has been done.
