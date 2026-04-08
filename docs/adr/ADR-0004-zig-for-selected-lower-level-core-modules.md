# ADR-0004: Use Zig for selected lower-level core modules, not necessarily for the whole first version

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** zig, systems, language-selection
- **Origin:** language selection discussion
- **Related:** ADR-0002, ADR-0006

## Context

There is strong interest in using this project to learn through building lower-level software. Zig is attractive because it offers native compilation, explicit control, good C interop, built-in testing, JSON support, and threading support.
At the same time, using Zig for the entire first version would increase ecosystem friction and slow iteration.

## Decision

We will treat **Zig as a strong candidate for selected core modules**, especially where lower-level control or performance matters, but we will **not require the entire first version to be implemented in Zig**.

Good candidates include:
- schema graph / dependency planner
- deterministic row-planning core
- validation kernel
- narrow parsing or normalisation components

## Alternatives considered

### Full Zig from the start
Pros:
- maximum systems-learning value
- single-language purity

Cons:
- slower iteration
- more ecosystem friction

### No Zig at all
Pros:
- simpler delivery

Cons:
- loses the lower-level learning goal

### Zig for selected modules
Pros:
- balances learning and practicality
- keeps risk bounded
- supports reusable focused libraries

Cons:
- polyglot complexity

## Consequences

### Positive
- We can build serious systems-oriented pieces without betting the entire project on ecosystem maturity.
- Zig can produce reusable public libraries or sharp CLI tools.

### Negative
- Interop and packaging need discipline.

### Follow-up
- Choose Zig only for modules with clear justification.
- Avoid language-driven architecture decisions.
