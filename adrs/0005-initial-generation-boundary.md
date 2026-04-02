# ADR 0005: Initial Generation Boundary

## Status

Accepted

## Context

ArchSpec states that code and formal deliverables should be derived from manifests, but the first operational milestone cannot safely generate everything at once.

The framework therefore needed an explicit decision about which outputs should be generated first.

Without this boundary:

- generator work would sprawl too early,
- contract design would become unstable,
- and the framework could overpromise automation before validation and capability models are ready.

## Decision

The initial generation boundary for ArchSpec will target:

- diagrams,
- API contract skeletons,
- ORM model skeletons,
- migration skeletons,
- document templates.

These targets are the first generation scope because they are:

- high-value,
- relatively low-risk,
- structurally derivable from manifests,
- and useful for proving that the framework can turn specifications into repeatable outputs.

The initial generation boundary does not include:

- full application generation,
- complete UI implementation,
- full backend business logic generation,
- or complete deployment automation from manifests alone.

## Consequences

### Positive

- The framework can prove derivation value without requiring a full compiler.
- The first generators can be scoped around stable, testable artifacts.
- Manifest design can mature under realistic pressure without forcing total automation too early.

### Costs

- Users must still accept a hybrid phase where some outputs are generated and some are implemented manually.
- Output ownership rules must be defined to avoid confusion between generated and handwritten files.
- Generator expectations must stay clearly bounded in the documentation.

## Immediate implications

The next framework work should define:

1. generator input and output conventions,
2. an intermediate representation strategy where needed,
3. generated-versus-handwritten ownership rules,
4. regeneration behavior,
5. template or generator module boundaries for the first artifact types.

## Non-goals

This decision does not imply:

- that ArchSpec is only a document generator,
- that the framework will never generate larger implementation slices later,
- or that complete runtime applications should be generated before schemas and capability contracts are stable.
