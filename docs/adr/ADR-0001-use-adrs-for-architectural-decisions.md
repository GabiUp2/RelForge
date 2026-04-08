# ADR-0001: Use ADRs for architectural decisions

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** process, architecture, documentation
- **Origin:** design discussion during early project exploration
- **Related:** ADR-0002, ADR-0003, ADR-0004, ADR-0005, ADR-0006

## Context

The project is exploratory, modular, and likely to evolve through experimentation.
We want to preserve the reasoning behind important decisions and avoid repeatedly re-arguing already settled trade-offs.

## Decision

We will keep a dedicated `docs/adr/` folder containing Architecture Decision Records (ADRs).
Every meaningful architectural or technical decision should be captured as an ADR once it is considered stable enough to matter.

## Alternatives considered

### Keep decisions only in chat history
Pros:
- zero overhead

Cons:
- poor discoverability
- reasoning becomes fragmented
- difficult to trace later

### Keep a single evolving architecture notes document
Pros:
- simple

Cons:
- weak decision traceability
- history becomes blurred

### Use ADRs
Pros:
- explicit decision traceability
- preserves rationale
- supports change over time
- familiar pattern

Cons:
- small documentation overhead

## Consequences

### Positive
- Decisions become auditable.
- Future changes can reference earlier reasoning.
- Public/open-source extraction becomes easier.

### Negative
- Requires judgment about what is ADR-worthy.

### Follow-up
- Create the initial ADR set.
- Add new ADRs when major architecture or tooling choices are made.
