# Architecture Overview

## Project direction

This project is being developed as:

- a learning vehicle,
- a systems/design exercise,
- a modular tooling experiment,
- and a potential source of reusable open-source libraries.

It is not being optimised primarily as a rushed internal deliverable.

## Design goals

- Learn through building.
- Keep module boundaries explicit.
- Use Python for orchestration, testing, and mocks.
- Use lower-level languages selectively where they provide real value.
- Keep logging strong and development visibility practical.
- Make future extraction of useful libraries possible.

## Non-goals for early versions

- full enterprise observability stack
- universal support for all databases from day one
- over-designed plugin ecosystem before core boundaries stabilise
- premature micro-module fragmentation

## Initial shape

Likely early modules:

- `schema-extract`
- `schema-normalize`
- `schema-plan`
- `data-generate`
- `validate-data`
- `py-orchestrator`
