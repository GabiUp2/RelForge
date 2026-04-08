# ADR-0003: Use JSON as the boundary format between modules

- **Status:** accepted
- **Date:** 2026-04-08
- **Deciders:** Bartosz
- **Tags:** interfaces, json, modularity
- **Origin:** modular system design discussion
- **Related:** ADR-0002, ADR-0006

## Context

The project will likely consist of multiple focused modules that need to exchange structured information, such as extracted schema metadata, canonical schema models, generation plans, validation reports, and run summaries.
We need a boundary format that is easy to inspect, easy to diff, and easy to mock in Python.

## Decision

Modules will communicate using **JSON** as the default boundary format.

## Alternatives considered

### XML
Pros:
- expressive
- familiar in some DB tooling ecosystems

Cons:
- heavier
- less convenient for quick inspection and Python-first mocking

### Custom binary format
Pros:
- efficient

Cons:
- poor inspectability
- premature optimisation

### JSON
Pros:
- widely supported
- easy for Python, Zig, and CLI tooling
- diff-friendly
- easy to mock and version

Cons:
- verbose
- schema evolution needs discipline

## Consequences

### Positive
- Module boundaries stay transparent.
- Test fixtures stay easy to create and maintain.
- Inter-process composition stays simple.

### Negative
- Some payloads may be large.

### Follow-up
- Define canonical JSON model(s) once the first module contracts stabilise.
