# ADR 0001: Framework Operating Mode

## Status

Accepted

## Context

ArchSpec is being defined as a reusable spec-first framework rather than as a one-off application repository.

One of the most important unresolved decisions was the framework operating mode:

- `spec-first`
- `spec-anchored`
- `spec-as-source`

This decision controls:

- how formal the manifests must become,
- how deterministic generation must be,
- how much manual coding is acceptable,
- how validation and drift detection must work,
- and how complete the product and architecture metamodels must be.

## Decision

ArchSpec targets `spec-as-source`.

In this repository, `spec-as-source` means:

- the manifests are expected to be detailed enough to map to implementation almost literally,
- the codebase is primarily a realization of the manifests,
- framework evolution must optimize for machine validation and deterministic derivation,
- and missing implementation behavior should be treated first as missing specification structure.

This does not require all code to be generated immediately.

It does require the framework contracts to evolve toward a level of precision where code generation, artifact derivation, and conformance checking are natural outcomes rather than aspirational ideas.

## Consequences

### Positive

- Stronger alignment with the purpose of ArchSpec.
- Lower tolerance for undocumented behavior.
- Better fit for AI-assisted development.
- Better support for regeneration and drift detection.
- Stronger separation between intent and implementation.

### Costs

- The manifest schemas must become much richer.
- Capability contracts must become formal.
- Product specs must carry more structured detail.
- Validation and CI become mandatory, not optional.
- Generator design becomes a core part of the framework, not an accessory.

## Immediate implications

The next framework work should prioritize:

1. manifest schemas,
2. compatibility and versioning rules,
3. capability contract formalization,
4. richer product metamodels,
5. deterministic generation boundaries,
6. validator and CI enforcement.

## Non-goals

This decision does not imply:

- generating every line of code from day one,
- prohibiting all handwritten code,
- or committing to one generator engine before the contracts are stable.

It only commits the framework to a destination where specifications are authoritative enough to drive code and derived artifacts almost directly.
