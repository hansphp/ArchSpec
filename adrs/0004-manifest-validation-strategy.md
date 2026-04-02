# ADR 0004: Manifest Validation Strategy

## Status

Accepted

## Context

ArchSpec depends on manifests as authoritative contracts, but those manifests are not yet formally machine-validatable.

The framework therefore needed an explicit validation strategy for:

- structural validation of individual manifests,
- semantic rules that span multiple manifests,
- versioning and compatibility expectations,
- and future automation such as generators, CI checks, and drift detection.

The main options considered were:

- JSON Schema,
- an OpenAPI-like structure definition style,
- or a custom validator only.

## Decision

ArchSpec will use:

- JSON Schema for manifest contracts,
- plus a thin semantic validator for cross-file and higher-order rules.

The intended shape is:

- one schema for `project-spec.yaml`,
- one schema for `scaffold/architecture-manifest.yaml`,
- one schema for `products/<slug>/product-spec.yaml`,
- structural validation handled by schemas,
- semantic validation handled by a framework validator layer.

The semantic validator is responsible for rules such as:

- cross-file references,
- active product and architecture consistency,
- capability-to-product compatibility,
- compatibility policy enforcement,
- and deprecation or evolution checks that are awkward to express in pure schema form.

## Consequences

### Positive

- The framework gains an interoperable and tool-friendly contract layer.
- JSON Schema keeps the validation model understandable to humans, AI agents, and tooling.
- Cross-file rules can stay precise without overloading the schemas.
- CI and local validation become easier to implement incrementally.

### Costs

- Validation is split across two layers and must be kept coherent.
- The repository must define manifest metadata such as version and schema identity.
- Compatibility and deprecation rules must be written explicitly rather than implied.

## Immediate implications

The next framework work should include:

1. create `schemas/workspace.schema.json`,
2. create `schemas/architecture-manifest.schema.json`,
3. create `schemas/product-spec.schema.json`,
4. add `manifest_version` to manifests,
5. add validation metadata such as schema identity,
6. define compatibility and deprecation policy.

## Non-goals

This decision does not imply:

- putting every semantic rule into JSON Schema,
- relying on a custom validator without explicit schemas,
- or reusing OpenAPI as the primary manifest contract language.
