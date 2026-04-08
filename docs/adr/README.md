# Architecture Decision Records

This directory stores Architecture Decision Records (ADRs).

## Purpose

ADRs capture important technical and architectural decisions so that we can trace:

- what was decided,
- why it was decided,
- what alternatives were considered,
- and what consequences follow from it.

This is especially important in this project because:

- the system is intentionally modular,
- part of the goal is learning through implementation,
- some components may be extracted into reusable libraries,
- and some decisions are made experimentally and should remain auditable later.

## ADR lifecycle statuses

Recommended statuses:

- `proposed`
- `accepted`
- `deprecated`
- `superseded`

## Rules

1. Do not rewrite history.
2. If a decision changes, create a new ADR.
3. Link related ADRs.
4. Prefer concrete consequences over vague philosophy.
5. Keep the rationale crisp and technical.

## Naming

Use:

- `ADR-0001-short-kebab-case-title.md`
- `ADR-0002-another-decision.md`

## Template

Use `ADR-0000-template.md`.
