# ADR 0002: Product Source Root Convention and Tracking Boundary

## Status

Accepted

## Context

ArchSpec already defined the source-of-truth manifests for workspace composition, reusable architecture, and product definition.

What it still lacked was a physical convention for where the product artifacts should be developed.

Without this, the framework had two practical problems:

- no explicit separation between framework files and product runtime files,
- and no clear boundary between framework governance tooling and application delivery tooling.

The initial wording around `source/` also left open an ambiguity about ownership:

- whether `source/` was a framework-tracked subtree,
- or a reserved workspace where a separate product repository could be created.

## Decision

ArchSpec adopts:

- `source/` as the product workspace chroot,
- and an explicit boundary where framework backlog tracking stays outside the framework repository.

### Tracking boundary

For framework work:

- backlog and planning are expected to live outside the repository,
- for example in GitHub Issues, GitHub Projects, or equivalent tooling,
- and the framework root should not carry an internal backlog structure unless the user explicitly asks for one.

For product work:

- a concrete product may later define its own backlog, delivery log, or operational memory,
- but that structure belongs in the product repository under `source/`, not at the framework root.

### Source root

The product source and runtime files must live under:

- `source/`

This path is reserved as the root of the product repository.

In the framework repository:

- `source/` should stay absent or empty until the product repository is cloned or initialized,
- the framework should not keep placeholder application files there,
- and the product repository may own its own `.git` directory under `source/`.

For web applications, the default internal application root is:

- `source/src/`

Runtime files such as:

- `source/Dockerfile`

belong inside the source root rather than at the framework root.

## Consequences

### Positive

- Clear separation between framework assets and product assets.
- Better fit for future generators and validators.
- Clear Git boundary between the framework repository and the product repository.
- Clear separation between framework governance tooling and product delivery tooling.

### Costs

- The framework no longer carries its own in-repo operational memory.
- Teams must rely on external planning tools for framework backlog work.

## Immediate implications

The framework should now evolve with:

1. stronger manifest contracts,
2. schemas and validators,
3. generators writing outputs into `source/`,
4. product-level delivery conventions only when a concrete application actually needs them.
