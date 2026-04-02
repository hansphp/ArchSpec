# ADR 0003: Framework Execution Model

## Status

Accepted

## Context

After adopting `spec-as-source` as the target operating mode, ArchSpec still needed to define its executable form.

The unresolved question was whether the framework should behave primarily as:

- a repository convention,
- an interactive Codex-mediated framework,
- a validator plus conventions,
- a generator-driven framework,
- or a full compiler-style framework.

This decision affects:

- how much formal validation is required before code generation,
- how much automation should exist in the first operational milestone,
- how aggressively the repository should introduce generators,
- and how quickly the framework can become enforceable without overcommitting to a large execution engine too early.

## Decision

ArchSpec will start as:

- `interactive conventions + validators + optional selective generators`

In practice, this means:

- manifests remain the primary source of truth,
- guided Codex interactions are the primary way to turn manifests into code and formal deliverables,
- conventions define repository structure and ownership boundaries,
- validators enforce structural and semantic correctness,
- generators are introduced selectively for high-value artifacts where they help,
- and handwritten implementation may still exist, but only as a disciplined realization of manifest intent.

ArchSpec is therefore not, at this stage:

- only a repository convention,
- a generator-first framework,
- or a full compiler-style system.

## Consequences

### Positive

- The path from concept to operability stays realistic.
- Validation can arrive before large-scale generation.
- The repository can enforce framework discipline earlier.
- The framework can prove value through shared interactive conventions before larger automation investments.
- AI-assisted work gains a clearer contract for what is validated versus what is still guided.

### Costs

- Some implementation work will remain partially guided rather than fully generated for a while.
- The repository must maintain both conventions and enforcement logic.
- Teams must tolerate an intermediate stage where validation is stronger than generation.
- Optional generator scope must be actively limited to avoid drifting into accidental framework complexity.

## Immediate implications

The next framework work should prioritize:

1. manifest schemas,
2. a validator entrypoint,
3. semantic cross-file validation rules,
4. capability contracts that can drive enforcement,
5. reusable interaction patterns, templates, or selective generators for a small first artifact set.

## Non-goals

This decision does not imply:

- building a full compiler before the contracts are stable,
- generating every application artifact from day one,
- treating convention-only documentation as sufficient enforcement,
- or allowing generators to define business behavior that should remain in manifests.
