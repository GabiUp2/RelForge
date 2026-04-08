# ADR-0006: Prefer Unix-style small, sharp modules over an early monolith

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** modularity, unix, architecture
- **Origin:** system decomposition discussion
- **Related:** ADR-0002, ADR-0003, ADR-0004

## Context

The project is intended to be educational, modular, reusable, and possibly a source of public libraries.
A monolithic implementation would make experimentation easier at first, but it would reduce clarity of boundaries and weaken the chance of extracting genuinely useful libraries.
At the same time, over-modularisation too early would create needless complexity.

## Decision

We will prefer **small, sharp modules** with clear responsibilities, inspired by the Unix philosophy: do one thing, do it well, and expose a clean contract.

Likely early modules include:
- schema extraction
- schema normalisation
- planning / dependency graph
- data generation
- validation
- Python orchestration

## Alternatives considered

### Early monolith
Pros:
- simple to start
- low coordination overhead

Cons:
- blurred boundaries
- harder extraction into libraries

### Highly fragmented micro-module architecture from day one
Pros:
- maximum separation

Cons:
- premature complexity
- too much ceremony

### Small set of meaningful modules
Pros:
- clean architecture
- realistic complexity
- supports reuse

Cons:
- requires care in defining interfaces

## Consequences

### Positive
- Module contracts become intentional.
- Some modules may later be released independently.
- Testing can target individual responsibilities cleanly.

### Negative
- More interface design effort up front.
- Some refactoring of boundaries is likely as understanding improves.

### Follow-up
- Start with a handful of meaningful modules, not dozens.
- Revisit boundaries only when real pressure appears.
