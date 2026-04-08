# ADR-0002: Adopt a hybrid architecture with Python orchestration and single-purpose modules

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** architecture, python, modularity
- **Origin:** project direction discussion
- **Related:** ADR-0003, ADR-0004, ADR-0006

## Context

The project has two competing needs:

1. Fast experimentation, mocks, integration testing, and orchestration.
2. Space for lower-level engineering in focused modules.

A single-language monolith would force an unnecessary compromise.

## Decision

We will use a hybrid architecture:

- **Python** for orchestration, mocks, developer tooling, integration testing, and end-to-end harnesses.
- Lower-level modules may be implemented in **Zig** or another systems language where this gives real engineering value.

## Alternatives considered

### Pure Python
Pros:
- fastest iteration
- strongest ecosystem

Cons:
- weaker systems-programming learning value for core modules

### Pure Zig
Pros:
- maximum systems-learning value
- single-language purity

Cons:
- slower iteration
- more ecosystem friction

### Hybrid architecture
Pros:
- balances speed and depth
- easier end-to-end testing
- supports reusable low-level modules

Cons:
- polyglot complexity
- requires clear module contracts

## Consequences

### Positive
- The project remains agile.
- Lower-level components can be introduced where justified.
- Python can provide fixtures, mocks, and scenario runners.

### Negative
- Build and packaging become slightly more complex.

### Follow-up
- Define module boundaries clearly.
- Standardise inter-module input/output contracts.
