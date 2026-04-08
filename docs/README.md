# Documentation

This folder contains project documentation for architecture, engineering decisions, and development guidance.

## Structure

- `architecture/` — higher-level design docs that describe how the system is meant to work.
- `adr/` — Architecture Decision Records (ADRs), one file per significant decision.

## Why ADRs

This project is exploratory and educational, but it is also intended to produce reusable engineering artefacts.
Because of that, important decisions should be recorded together with:

- the context that led to them,
- alternatives that were considered,
- the final decision,
- the consequences and trade-offs,
- and links to related docs or follow-up ADRs.

## ADR conventions

- One ADR per decision.
- ADRs are immutable once accepted, except for small editorial fixes.
- If a decision changes, create a new ADR and mark the old one as superseded.
- Use incremental numbering: `ADR-0001`, `ADR-0002`, etc.

See `adr/README.md` and `adr/ADR-0000-template.md`.
