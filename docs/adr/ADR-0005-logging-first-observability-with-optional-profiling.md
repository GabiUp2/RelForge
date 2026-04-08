# ADR-0005: Prefer strong structured logging with optional profiling over a full observability stack

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** logging, profiling, observability
- **Origin:** runtime visibility and development tooling discussion
- **Related:** ADR-0002

## Context

The system is intended to be composed of small, focused modules. A full distributed observability stack is not a natural fit at this stage because the modules are expected to work together as a small unit and the project is exploratory.
At the same time, we want strong verbose logging during development, a clear production-safe `INFO` layer, and ways to inspect performance visually during development.

## Decision

We will prioritise:

1. strong structured logging
2. clear `INFO`-level production logs
3. optional profiling and tracing for development

We will not start with a full distributed observability stack.

## Alternatives considered

### Full observability stack from the beginning
Pros:
- rich telemetry

Cons:
- heavy
- mismatched to current system scale
- distracts from core engineering work

### Minimal plain-text logs only
Pros:
- simple

Cons:
- weak machine-readability
- weak automation and test support

### Structured logging with optional profiling
Pros:
- pragmatic
- good fit for modular CLI tools
- supports both development and production needs

Cons:
- requires log contract discipline

## Consequences

### Positive
- Runtime behaviour remains inspectable.
- Development remains lightweight.
- Profiling can be turned on only when needed.

### Negative
- No all-in-one telemetry platform initially.

### Follow-up
- Standardise log schema, scopes, levels, and trace flags.
- Keep a separate architecture doc for logging and profiling conventions.
