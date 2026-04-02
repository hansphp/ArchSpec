# ArchSpec Framework Gap Analysis

This document translates the current state of ArchSpec into:

- a file-by-file gap analysis,
- a maturity assessment,
- and a prioritized backlog for evolving the repository from a well-defined concept into an operable framework.

It is focused on the framework itself, not only on the current example product.

## Executive summary

ArchSpec already has a strong conceptual foundation.

It clearly expresses:

- a spec-first philosophy,
- separation between reusable architecture and product-specific definition,
- a lifecycle and deliverables mindset,
- and a methodological base grounded in software engineering and Spec-Driven Development.

What is still missing is the layer that makes the framework operational rather than only well-described.

In practical terms, the biggest gaps are:

- no formal machine-validatable manifest schemas,
- no explicit compatibility and versioning policy for manifests,
- no executable generation contract,
- no capability contract model detailed enough for automation,
- no validator or CI enforcement,
- no template or generator structure,
- no second product or second architecture profile proving reusability,
- and no reference implementation pipeline demonstrating the framework end to end.

The project is currently strong in:

- intent,
- structure,
- methodology,
- lifecycle framing.

The project is currently weak in:

- formalization,
- enforcement,
- automation,
- proof of reuse.

Note:

- The repository now defines a `source/` product workspace convention and a clearer boundary between framework governance and product delivery tracking.
- Those additions improve structural clarity, but they do not yet replace the need for schemas, validators, and generation mechanics.

## Current maturity snapshot

| Dimension | Current state | Assessment |
|---|---|---|
| Framework purpose | Clearly defined | Strong |
| Manifest layering | Clearly defined | Strong |
| Methodological grounding | Clearly defined | Strong |
| Lifecycle and deliverables model | Defined | Medium-Strong |
| Manifest formalization | Not formalized | Weak |
| Validation and governance automation | Not implemented | Weak |
| Capability contract model | Partially defined | Weak-Medium |
| Generation model | Only implied | Weak |
| Reusability proof | One example product only | Weak |
| Framework operability | Not yet executable | Weak |

## What the repository already solves well

- It separates workspace composition from reusable architecture and product definition.
- It gives the repository a coherent spec-first identity.
- It positions the current product as a validation case, not as the permanent identity of the framework.
- It defines a useful lifecycle and deliverables language.
- It provides a curated methodological base for future AI-assisted work.
- It already avoids the biggest conceptual failure mode: mixing framework intent with one product's business logic.

That is important because many framework efforts fail before this point.

ArchSpec has already crossed the "unclear idea" stage.

It has not yet crossed the "operable framework" stage.

## File-by-file gap analysis

### `AGENTS.md`

Current value:

- Defines how agents should interpret the repository.
- Establishes authority order.
- Reinforces the separation between scaffolding and product.
- Integrates `REFERENCES.md` as contextual methodological grounding.

What is missing:

- A required reading sequence for different task types.
- A definition of what evidence an agent must produce before considering a framework change complete.
- A policy for framework-level change types such as:
  - new manifest version,
  - new capability module,
  - new generator,
  - new profile,
  - breaking schema change.
- A minimum validation checklist for closing work.
- A distinction between:
  - concept-only changes,
  - contract changes,
  - generator changes,
  - product changes.

Why it matters:

Without this, agent behavior is directionally good but not yet operationally strict.

Recommended next step:

- Add a "Framework Change Types" section.
- Add a "Minimum Completion Evidence" section.
- Add a "Required validation before close-out" section.

Priority:

- Medium

### `project-spec.yaml`

Current value:

- Defines the workspace composition.
- Identifies the active architecture manifest.
- Identifies the active product through a reusable slug placeholder.
- Declares derived artifact categories.
- Describes where future products should live.

What is missing:

- A `manifest_version` field with compatibility meaning.
- A `schema_ref` or equivalent contract reference.
- A registry of available products instead of only the active one.
- A registry of available architecture manifests or profiles.
- Output directory conventions for generated artifacts.
- A definition of the active generation mode:
  - documentation-only,
  - validation-enabled,
  - codegen-enabled,
  - full regeneration.
- A definition of mandatory vs optional derived artifacts.
- A lifecycle status model for the framework itself.
- A deliverable policy that connects the lifecycle roadmap to actual repository outputs.
- A compatibility and deprecation policy for changing the composition contract.

Why it matters:

This file currently states composition intent, but it does not yet fully control composition as an executable contract.

Recommended next step:

- Add manifest metadata and schema identity.
- Add explicit product and architecture registries.
- Add generation mode and artifact output conventions.
- Add compatibility policy fields.

Priority:

- Critical

### `scaffold/architecture-manifest.yaml`

Current value:

- Defines the technical profile.
- Defines reusable capability modules.
- Defines variation points.
- Defines a first generation contract and basic playbooks.

What is missing:

- A formal capability contract model.
- Capability inputs, outputs, dependencies, and extension points.
- A distinction between:
  - cross-cutting capabilities,
  - UI capabilities,
  - data capabilities,
  - integration capabilities,
  - operational capabilities.
- Security architecture defaults.
- Observability defaults.
- Identity and access defaults.
- Configuration and environment strategy.
- Packaging and repository conventions.
- Architecture profile support beyond a single embedded profile.
- A mapping from capability modules to generated layers.
- A mapping from variation points to supported generators or templates.
- A quality gate policy.
- A naming convention policy for generated modules and files.

Why it matters:

This file is the most important missing bridge between "architecture definition" and "framework execution".

Today it describes the stack.

It does not yet define how the stack behaves as a reusable architecture engine.

Recommended next step:

- Convert `capability_modules` from labels into structured contracts.
- Add cross-cutting platform capabilities such as:
  - authentication,
  - authorization,
  - auditing,
  - observability,
  - file storage,
  - notifications,
  - background jobs,
  - search,
  - caching,
  - feature flags.
- Define architecture profiles explicitly.

Priority:

- Critical

### `products/<slug>/product-spec.yaml`

Current value:

- Defines a concrete product purpose.
- Lists required capabilities.
- Defines detailed actors, roles, and permissions.
- Defines core entities and field validations.
- Defines business constraints and state models.
- Defines use cases and workflows.
- Defines UI modules.
- Defines structured reports, imports, and exports.
- Defines non-functional requirements and acceptance criteria.
- Defines sample scenarios, glossary entries, and an evolution playbook.
- Includes one evolution playbook.

What is missing:

- Canonical interface and API contract expectations.
- A stricter convention for machine-readable error definitions and result envelopes.
- Resolution of remaining relational ambiguities such as:
  - whether `Capacidad.cursos_ids` stays denormalized or becomes an explicit join model,
  - whether leader ownership is represented canonically by `lider_responsable_id`, `LiderPersona`, or both.
- Example datasets or richer executable examples for future validation and testing.
- Binding to a formal schema once manifest schemas are introduced.

Why it matters:

The product spec is now strong enough to support design derivation, workflow reasoning, and a much more disciplined implementation conversation.

It is still not fully machine-operable until the framework adds schemas, canonical modeling rules, and interface contracts that remove the last interpretation gaps.

Recommended next step:

- Use this enriched product spec as the baseline input for the formal product schema.
- Resolve the remaining canonical modeling ambiguities before generator work begins.
- Add interface and API contract sections once the schema layer exists.

Priority:

- Medium-Critical

### `README.md`

Current value:

- Explains the framework clearly.
- Describes the three manifest layers.
- Gives a strong onboarding explanation.
- Explains how to classify changes.
- Documents the major framework components and why they exist.
- Includes a lifecycle section with a condensed working diagram.
- Includes a worked example for building a product with Codex.

What is missing:

- A schema-validation quickstart once manifest schemas exist.
- A generator quickstart once generator modules exist.
- A future structure map for framework directories such as:
  - `schemas/`,
  - `templates/`,
  - `generators/`,
  - `deliverables/`.
- Ongoing synchronization with actual framework maturity so examples do not imply more automation than the repository currently supports.

Why it matters:

The README is now a strong operational entry point, but it will only remain trustworthy if it keeps clearly distinguishing:

- what the framework can do today,
- and what the framework is designed to do after schemas, validators, and generators exist.

Recommended next step:

- Add schema and generator quickstarts when those capabilities are implemented.
- Keep the worked example aligned to the real maturity of the framework.

Priority:

- Medium

### `LIFECYCLE-ROADMAP.md`

Current value:

- Defines a full lifecycle.
- Defines phase gates.
- Defines a deliverables catalog.
- Gives the framework a strong engineering process backbone.

What is missing:

- A direct mapping from lifecycle phases to repository directories.
- A direct mapping from lifecycle phases to manifest owners.
- A minimal ArchSpec-specific mandatory artifact pack.
- A tracking template for progress through the lifecycle.
- A distinction between:
  - framework lifecycle,
  - product lifecycle,
  - generated-solution lifecycle.

Why it matters:

The lifecycle is rich, but it is still abstract.

It needs an operational repository mapping.

Recommended next step:

- Add a future artifact storage convention after `deliverables/` is introduced.
- Add "framework lifecycle vs product lifecycle" mapping.

Priority:

- Medium

### `REFERENCES.md`

Current value:

- Synthesizes the reference archive into a curated knowledge base for the AI.
- Defines stable heuristics.
- Protects the repository from treating raw research notes as the source of truth.

What is missing:

- A concept-to-decision map showing which ideas are already adopted by ArchSpec and which remain only advisory.
- A "current commitments vs future options" distinction.
- A bibliography section that links concepts to expected framework modules.

Why it matters:

Right now the file is strong as methodology.

It is less strong as a decision support map.

Recommended next step:

- Add a section later titled "Adopted framework commitments".

Priority:

- Low-Medium

### Overall repository structure

Current value:

- Minimal and clean.
- Good for early conceptual work.

What is missing:

- `schemas/`
- `templates/`
- `generators/`
- `profiles/`
- `deliverables/`
- `examples/` or a second product
- `policies/` or `governance/`
- CI configuration
- validator entrypoint

Why it matters:

The repository currently defines the framework, but does not yet physically embody its execution model.

Recommended next step:

- Introduce the structural directories only after the formal contracts are decided.

Implemented baseline:

- `source/` as the product workspace chroot
- framework tracking kept outside the framework repository

Priority:

- High

## Cross-cutting missing definitions

These gaps do not belong to one file only.

They are framework-wide.

### 1. Manifest formalization

Missing:

- manifest schemas,
- semantic versioning rules,
- compatibility policy,
- deprecation policy,
- schema migration policy.

Impact:

- The framework cannot validate itself.
- Future automation will be fragile.

### 2. Capability contract model

Missing:

- required inputs,
- expected outputs,
- generation targets,
- dependencies,
- composition rules,
- testing expectations,
- extension points.

Impact:

- Capabilities are descriptive, not operational.

### 3. Generation model

Missing:

- a pipeline definition,
- intermediate representation rules,
- generator boundaries,
- output ownership rules,
- generated vs handwritten file policy,
- regeneration policy.

Impact:

- "code is derived from manifests" is true in principle, but not yet executable.

### 4. Validation and governance

Missing:

- manifest validation,
- linting rules,
- CI policy,
- drift detection,
- architecture compliance checks,
- artifact completeness checks.

Impact:

- The framework cannot yet enforce its own philosophy.

### 5. Reusability proof

Missing:

- second product,
- second architecture profile,
- or both.

Impact:

- The framework is still validated only against one product and one stack profile.

### 6. Product completeness model

Missing:

- enough structure in the product spec to drive implementation deterministically.

Impact:

- The framework still depends on human interpretation for too many decisions.

## Critical decisions you should settle first

Before implementing generators or validators, these decisions should be made explicitly.

### Decision 1. What is the target operating mode?

Choose the intended ArchSpec target:

- `spec-anchored`
- `spec-as-source`

Decision:

- ArchSpec targets `spec-as-source`.

Why:

- The framework is intended to produce manifests that can pass into code and derived artifacts almost literally.
- This is more aligned with the repository purpose than stopping at a lighter spec-anchored posture.
- It increases the importance of schemas, capability contracts, validation, and deterministic generation.

### Decision 2. What is the executable form of the framework?

Choose whether ArchSpec is primarily:

- repository convention,
- validator plus conventions,
- generator-driven framework,
- or full compiler-style framework.

Recommendation:

- Start as `validator + conventions + selective generators`.

Why:

- It is the safest path from concept to operability.

### Decision 3. What is the schema strategy?

Choose how manifests will be formally validated.

Options:

- JSON Schema
- OpenAPI-like schema style for data structures
- custom validator only

Recommendation:

- Use JSON Schema for manifest contracts plus a thin semantic validator for cross-file rules.

Why:

- It is interoperable, AI-friendly, and easy to automate.

### Decision 4. What is the framework's generation boundary?

Choose what ArchSpec will generate first.

Recommendation:

- First generation targets should be:
  - diagrams,
  - API contract skeletons,
  - ORM model skeletons,
  - migration skeletons,
  - document templates.

Why:

- These are high-value and relatively low-risk artifacts.

### Decision 5. What proves reuse?

Choose how you will prove the framework is not single-product.

Recommendation:

- Add one second product before broadening generator complexity.

Why:

- Reuse proof is more important than generator sophistication at this stage.

## Priority backlog

The backlog below is ordered by dependency and expected leverage.

### P0. Lock the framework strategy

Goal:

- Freeze the core strategic decisions that all later work depends on.

Tasks:

- [ ] Define the target operating mode of ArchSpec.
- [ ] Define the intended execution model of the framework.
- [ ] Define the schema strategy.
- [ ] Define the initial generation boundary.
- [ ] Define what counts as proof of framework reuse.
- [ ] Record these decisions as ADRs.

Expected deliverables:

- Framework Strategy ADR
- Manifest Validation ADR
- Generation Boundary ADR
- Reuse Proof ADR

Done when:

- The above decisions are written and approved.

Priority:

- Immediate

### P1. Formalize the manifest contracts

Goal:

- Turn the current manifests into machine-validatable contracts.

Tasks:

- [ ] Create `schemas/workspace.schema.json`.
- [ ] Create `schemas/architecture-manifest.schema.json`.
- [ ] Create `schemas/product-spec.schema.json`.
- [ ] Add `manifest_version` to each manifest.
- [ ] Add schema references or validation metadata.
- [ ] Define compatibility rules for manifest evolution.
- [ ] Define deprecation rules for fields and sections.

Expected deliverables:

- Schema files
- Compatibility policy
- Manifest versioning policy

Done when:

- All manifests validate structurally.

Priority:

- Immediate

### P2. Define the capability contract model

Goal:

- Make architecture capabilities precise enough to drive generation and validation.

Tasks:

- [ ] Redesign `capability_modules` as structured objects.
- [ ] Add fields such as:
  - `purpose`
  - `required_product_inputs`
  - `generated_outputs`
  - `dependencies`
  - `quality_expectations`
  - `extension_points`
  - `applicability`
- [ ] Add missing cross-cutting capabilities.
- [ ] Map capabilities to generation layers.

Expected deliverables:

- Capability contract schema
- Updated architecture manifest
- Capability inventory

Done when:

- A product can request a capability and the framework can know what artifacts and rules follow from it.

Priority:

- Immediate

### P3. Upgrade the product metamodel

Goal:

- Make product specs complete enough to drive deterministic engineering work.

Tasks:

- [ ] Add sections for:
  - actors
  - roles
  - permissions
  - use cases
  - workflows
  - state transitions
  - validations
  - NFRs
  - report definitions
  - import/export definitions
  - acceptance criteria
- [ ] Define a product glossary convention.
- [ ] Upgrade `products/<slug>/product-spec.yaml`.
- [ ] Create a reusable product template.

Expected deliverables:

- Product spec schema extension
- Product template
- Upgraded example product

Done when:

- The product spec no longer requires major unstated assumptions for implementation.

Priority:

- Immediate

### P4. Introduce validation and governance automation

Goal:

- Make the framework enforceable.

Tasks:

- [ ] Create a validator entrypoint.
- [ ] Validate manifests in CI.
- [ ] Add lint rules for specs and metadata.
- [ ] Add drift detection policy.
- [ ] Add architecture compliance checks.
- [ ] Add required review policy for framework changes.

Expected deliverables:

- Validation script or CLI
- CI workflow
- Governance policy

Done when:

- Invalid manifests and broken contracts fail automatically.

Priority:

- High

### P5. Define the generation pipeline

Goal:

- Make "derived artifacts" concrete.

Tasks:

- [ ] Define an intermediate representation strategy.
- [ ] Define generator input and output conventions.
- [ ] Define generated-file ownership rules.
- [ ] Define regeneration behavior.
- [ ] Choose template engine or generator approach.

Expected deliverables:

- Generator architecture document
- Output conventions
- Regeneration policy

Done when:

- The repository can explain exactly how manifests become outputs.

Priority:

- High

### P6. Build the first generators

Goal:

- Prove the framework can produce useful outputs.

Tasks:

- [ ] Generate ER diagrams.
- [ ] Generate API contract skeletons.
- [ ] Generate ORM model skeletons.
- [ ] Generate migration skeletons.
- [ ] Generate baseline documentation artifacts.

Expected deliverables:

- Initial generator modules
- Example generated outputs

Done when:

- At least three artifact types are generated from manifests reproducibly.

Priority:

- High

### P7. Introduce deliverable and template structure

Goal:

- Align the lifecycle roadmap with a real repository layout.

Tasks:

- [ ] Create `deliverables/`.
- [ ] Create `templates/`.
- [ ] Add template documents for:
  - ADRs
  - architecture definition
  - technical specification
  - test strategy
  - release readiness
- [ ] Map lifecycle phases to directory conventions.

Expected deliverables:

- Deliverable structure
- Template packs

Done when:

- The lifecycle roadmap can be executed in the repo, not only described.

Priority:

- Medium-High

### P8. Prove reuse with a second product

Goal:

- Demonstrate that ArchSpec is not tied to one business domain.

Tasks:

- [ ] Create a second product under `products/`.
- [ ] Reuse the same architecture manifest.
- [ ] Validate both products with the same schemas.
- [ ] Compare capability reuse.

Expected deliverables:

- Second product spec
- Reuse comparison note

Done when:

- Two distinct products can coexist under the same framework.

Priority:

- Medium-High

### P9. Prove variation with a second architecture profile

Goal:

- Demonstrate that product intent is portable across architecture variants.

Tasks:

- [ ] Define a second architecture profile or manifest.
- [ ] Keep the product mostly unchanged.
- [ ] Show which outputs vary and which remain stable.

Expected deliverables:

- Second architecture manifest or profile
- Variation proof note

Done when:

- One product can be mapped to more than one architecture profile.

Priority:

- Medium

### P10. Build a minimal reference implementation

Goal:

- Demonstrate the framework end to end with a real generated or semi-generated application slice.

Tasks:

- [ ] Choose a narrow slice of the active product.
- [ ] Generate initial artifacts.
- [ ] Implement the remaining glue.
- [ ] Validate that the slice stays aligned to manifests.

Expected deliverables:

- Minimal reference app slice
- Validation evidence

Done when:

- The framework has a credible operational demonstration.

Priority:

- Medium

## Recommended execution sequence

If you want the shortest path to a credible framework, do this:

1. P0 - freeze the strategic decisions.
2. P1 - formalize manifest schemas.
3. P2 - formalize capability contracts.
4. P3 - enrich the product metamodel.
5. P4 - add validation and CI.
6. P5 - define the generation pipeline.
7. P6 - build the first generators.
8. P8 - add a second product.
9. P7 - expand deliverable templates and structure.
10. P9/P10 - prove variation and full operability.

## What should not be done yet

Avoid doing these too early:

- building a large generator before manifest schemas exist,
- expanding the DSL aggressively before compatibility policy exists,
- adding many architecture patterns before one is proven,
- treating the current product as the framework's permanent center,
- adding a second stack before proving the first one end to end,
- or overloading `project-spec.yaml` with all semantics.

## Immediate next milestone

The most important milestone from here is:

- move ArchSpec from "described framework" to "formally specified spec-as-source framework".

That milestone is complete when:

- manifests have schemas,
- capabilities have contracts,
- products have richer structure,
- validation exists,
- and at least one artifact type is derived reproducibly from manifests with minimal hidden interpretation.

## In short

ArchSpec does not currently suffer from lack of vision.

It suffers from lack of formalization and executable framework mechanics.

That is good news.

It means the next work is not "invent what this is".

The next work is:

- formalize it,
- validate it,
- operationalize it,
- and prove that it reuses cleanly.
