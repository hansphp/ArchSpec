# REFERENCES

This document synthesizes the contents of `deep-research-reports/` into an AI-facing methodological base for working with ArchSpec.

Its purpose is not to replace the source of truth of the repository.

Its purpose is to give the AI a stable conceptual foundation, shared vocabulary, and practical heuristics that improve decision-making when developing with this scaffolding.

## How to use this file

Use this file as:

- methodological background,
- conceptual grounding,
- engineering heuristics,
- architecture and governance context,
- and a source of stable cross-project patterns.

Do not use this file as:

- the active product definition,
- the active architecture definition,
- the active workspace composition,
- or permission to override repository manifests.

## Authority model

When working in this repository, the AI should treat sources in this order:

1. direct user instructions,
2. `project-spec.yaml`,
3. the active manifests referenced by `project-spec.yaml`,
4. `AGENTS.md`,
5. this `REFERENCES.md`,
6. implementation code,
7. raw files inside `deep-research-reports/`.

This means:

- `REFERENCES.md` provides context,
- but it does not override the active manifests,
- and it does not define business truth for any product by itself.

## What the references collectively establish

Across the reference set, there is a consistent position:

- software engineering is broader than coding,
- architecture should be explicit,
- requirements, design, implementation, testing, deployment, and maintenance form a feedback system,
- governance and quality controls are first-class concerns,
- structured specifications are more useful than vague intent when humans and AI collaborate,
- and reusable scaffolding is stronger when it separates stable architectural concerns from product-specific intent.

That is the conceptual base ArchSpec should preserve.

## Reference source map

The files under `deep-research-reports/` are intended to function as a manually refreshable state-of-the-art knowledge base.

That means:

- they should preserve stable concepts,
- they should be updated manually when the field changes meaningfully,
- and they should prefer clear factual framing over one-off exploratory report naming.

The synthesized ideas in this file are primarily derived from:

- `deep-research-reports/methodology.md`
- `deep-research-reports/pre-code-framework-landscape.md`
- `deep-research-reports/spec-driven-development-foundations.md`
- `deep-research-reports/owasp-asvs-reference.md`

Each file contributes a different angle:

- `methodology.md` provides software engineering, lifecycle, governance, quality, security, metrics, and architecture foundations.
- `pre-code-framework-landscape.md` explains the strategic positioning of ArchSpec-like work as a framework above direct code generation.
- `spec-driven-development-foundations.md` provides the strongest conceptual base for Spec-Driven Development as an engineering discipline.
- `owasp-asvs-reference.md` provides a structured factual reference for application-security verification requirements centered on OWASP ASVS.

## Core methodological facts the AI should assume

### 1. Software engineering is lifecycle engineering

The references treat software engineering as the disciplined practice of specifying, building, verifying, deploying, operating, and evolving software under explicit constraints.

The AI should therefore assume that a serious project must address:

- requirements,
- architecture,
- implementation,
- testing,
- delivery,
- operations,
- maintenance,
- governance,
- security,
- measurement.

If any of these are missing, the AI should identify the gap rather than silently pretend the project is complete.

### 2. The lifecycle is not linear

The references consistently describe the software lifecycle as a feedback system.

That means:

- testing can refine requirements,
- operational incidents can trigger redesign,
- architecture decisions can force requirement clarification,
- implementation constraints can reshape planning,
- and measurement should influence future changes.

The AI should avoid thinking in a naive one-way waterfall unless the user explicitly wants that style.

### 3. Standards and frameworks are useful because they reduce ambiguity

The references repeatedly rely on standards and formal frameworks to give shared structure.

The important implication is not “follow standards mechanically”.

The important implication is:

- use shared terminology,
- define artifacts explicitly,
- make ownership visible,
- and reduce ambiguity between roles and phases.

## Software engineering baseline

The references establish the following baseline view of software engineering:

- requirements engineering matters,
- architecture documentation matters,
- testing should be systematic,
- product quality should be defined and measured,
- security should be integrated through the lifecycle,
- maintenance is part of the system, not an afterthought,
- and engineering decisions should be traceable.

The AI should default to this posture when producing plans, architecture, or deliverables.

## Spec-Driven Development baseline

### Working definition

Spec-Driven Development is treated in the references as a discipline where structured specifications become authoritative enough to guide, generate, validate, or govern implementation.

The important idea is not only “write a spec first”.

The important idea is:

- the spec must shape downstream work,
- the spec must stay alive,
- and the system must be checked against the spec continuously enough to prevent drift.

### Levels of rigor

The references distinguish a useful spectrum:

- `spec-first`: the spec guides the first build, but may later become secondary.
- `spec-anchored`: the spec remains alive and is continuously checked against implementation.
- `spec-as-source`: the spec becomes the primary editable artifact and machines derive most implementation artifacts from it.

For ArchSpec, the accepted operating mode is `spec-as-source`.

The AI should therefore treat:

- `spec-first` and `spec-anchored` as useful comparison levels,
- but not as the repository's chosen target posture.

The repository may still be incomplete in automation terms, but its governing direction is already `spec-as-source`, not merely a transition toward it.

### SDD is broader than API contracts

The references are explicit that SDD is not limited to OpenAPI.

Structured specifications may include:

- business specs,
- API contracts,
- schema definitions,
- executable examples,
- invariants,
- acceptance rules,
- architecture constraints,
- migration rules,
- and tool-operable metadata.

The AI should not reduce ArchSpec to “generate an OpenAPI file”.

### SDD complements TDD, BDD, and related practices

The references present TDD, BDD, ATDD, and Specification by Example as complementary practices at different granularity levels.

The AI should assume:

- TDD helps define unit or component behavior,
- BDD and ATDD help define feature behavior,
- Specification by Example helps clarify requirement meaning,
- SDD provides the larger governance discipline that makes such artifacts authoritative across the lifecycle.

That means tests and examples are not separate from the specification world.

They are part of it.

## What ArchSpec specifically implies

The references strongly support the idea that ArchSpec should behave as a framework above any one code generator, template engine, or stack.

The AI should assume the intended differentiation of ArchSpec is:

- one reusable framework,
- multiple possible products,
- multiple possible derived artifacts,
- and platform mappings that remain secondary to intent.

The key ArchSpec idea is:

- stable intent should be separated from variable implementation targets.

This is conceptually aligned with:

- platform-independent modeling,
- software factory thinking,
- structured scaffolding,
- and spec-driven workflows.

## Separation principles the AI should preserve

Based on the references, the AI should preserve these separations whenever possible:

- architecture vs product,
- stable intent vs stack realization,
- specification vs implementation,
- reusable capability vs product-specific workflow,
- contract vs generated artifact,
- governance rules vs business rules.

If a change request mixes these layers, the AI should explicitly separate them before implementing.

## AGENTS.md and agent interoperability

The references point to ecosystem convergence around `AGENTS.md` as a repository-level instruction contract for coding agents.

The AI should treat `AGENTS.md` as:

- operational guidance,
- repository onboarding,
- behavior constraints,
- and a compatibility mechanism across agent tools.

The AI should not treat it as the product definition or architecture definition.

It is a control surface for agent behavior, not a substitute for the manifests.

## Product and scaffolding positioning

A central idea from the references is that a framework like ArchSpec should not be trapped as “just another app template”.

The AI should assume:

- the framework itself is a product,
- but its purpose is to help define and generate other products,
- and the current example product is evidence of the framework, not the framework’s permanent identity.

This is important whenever the AI proposes new files or structure.

It should bias toward reusable contracts, not one-off app-specific shortcuts.

## Multi-artifact mindset

The references argue that the output of a software definition should not be limited to source code.

The AI should assume that derived artifacts may include:

- application code,
- database schema and migrations,
- ER diagrams,
- architecture documents,
- ADRs,
- test assets,
- API contracts,
- mocks,
- reports,
- operational documentation,
- import and export templates,
- and governance evidence.

If a request sounds like “build the application”, the AI should still think in terms of the full artifact set, not only code.

## Tooling patterns supported by the references

The references consistently present a modern SDD toolchain pattern.

The AI should treat the following categories as valid building blocks:

- structured specs,
- specification linting,
- schema validation,
- mock and stub generation,
- code generation,
- contract testing,
- schema-based testing,
- CI/CD gating,
- structured outputs for AI pipelines.

Representative technologies mentioned in the references include:

- OpenAPI
- AsyncAPI
- JSON Schema
- Gherkin
- Pact
- Schemathesis
- Spectral
- Prism
- OpenAPI Generator
- Mermaid
- DBML
- PlantUML
- Cookiecutter
- Copier
- Backstage

The AI should treat these as examples and patterns, not hard requirements.

## Enforcement is mandatory if the spec is authoritative

One of the strongest repeated messages in the references is that specs decay unless they are enforced.

The AI should therefore assume:

- a spec without validation is at risk,
- a contract without tests is fragile,
- a diagram without regeneration rules becomes decorative,
- and documentation without review gates becomes stale.

When the AI proposes a spec-driven workflow, it should also propose at least some of these:

- linting,
- validation,
- drift detection,
- contract checks,
- schema checks,
- CI gates,
- formal review steps.

## Drift is a primary failure mode

The references repeatedly identify spec drift as the most important operational risk in spec-driven work.

The AI should assume drift can happen between:

- spec and code,
- spec and tests,
- spec and runtime behavior,
- business rules and contracts,
- architecture rules and actual topology,
- generated artifacts and their source manifests.

The AI should actively look for places where drift could emerge and recommend controls.

## Quality model assumptions

The references support a broad product quality view, not only correctness.

The AI should assume quality includes at least:

- functional suitability,
- performance efficiency,
- compatibility,
- usability,
- reliability,
- security,
- maintainability,
- portability,
- and lifecycle-level quality evidence.

When defining requirements or acceptance criteria, the AI should include non-functional concerns where relevant.

## Testing posture the AI should assume

The references support a layered testing strategy.

The AI should default to:

- many focused unit and integration tests,
- fewer end-to-end tests,
- explicit non-functional testing where risk justifies it,
- and continuous evidence collection in CI.

The AI should also recognize that tests can act as executable specifications when written at the right level.

## OWASP ASVS facts the AI should know

The security research set includes a concrete factual reference for OWASP ASVS, not only a generic "security matters" reminder.

The most important facts preserved from `deep-research-reports/owasp-asvs-reference.md` are:

- OWASP ASVS is an open standard of verifiable security requirements for web applications and web services.
- Its role is to define what should be verified, not to prescribe one implementation stack or one SDLC model.
- The current version captured in the research base is `ASVS 5.0.0`, released in `May 2025`.
- ASVS 5.0 organizes `345` requirements across `3` levels and `17` chapters.
- The level counts captured from the research base are `L1 = 70`, `L2 = 183`, and `L3 = 92`.
- `L1` is a low-friction baseline, `L2` is the recommended target for most serious applications, and `L3` is a higher-assurance profile with deeper verification burden.
- ASVS is best treated as a product-security verification standard for backend systems, web services, and APIs.
- ASVS does not by itself define a full secure SDLC, CI/CD model, or hosting/operations program.
- OWASP does not certify products, vendors, or verifiers under ASVS, so third-party "ASVS certification" claims are not official OWASP certification.
- ASVS should be paired with adjacent implementation and testing guidance such as the OWASP Cheat Sheet Series and the OWASP Web Security Testing Guide.
- For mobile systems, the better OWASP references are `MASVS` and `MASTG`, not ASVS alone.
- ASVS applicability is selective by chapter, so teams should map only the chapters relevant to the active product and architecture.

For ArchSpec, the practical implication is that security should be modeled as verifiable requirements and applicability decisions, not as vague "follow best practices" statements.

## Security posture the AI should assume

The references consistently treat security as a lifecycle concern, not a post-build activity.

The AI should assume secure development should include, where relevant:

- security requirements,
- secure design review,
- dependency and supply chain visibility,
- vulnerability management,
- secure configuration,
- release controls,
- operational security readiness.

The references specifically reinforce the importance of:

- secure development practices,
- OWASP-style application risk awareness,
- supply chain integrity,
- SBOM generation,
- vulnerability scoring and prioritization,
- and governance-compatible security processes.

## Governance posture the AI should assume

The references strongly support explicit technical governance.

The AI should assume healthy engineering governance includes:

- code review policies,
- required checks before merge,
- traceability from issue to release,
- decision records,
- configuration management,
- and explicit change control.

The AI should not assume that “working code” is enough evidence in a formal engineering process.

## Metrics posture the AI should assume

The references treat metrics as decision aids, not vanity numbers.

The AI should assume metrics should be used to improve the system, not to create false optimization pressure.

Relevant metric families from the references include:

- delivery flow metrics,
- stability metrics,
- defect and leakage metrics,
- quality metrics,
- spec quality metrics,
- drift metrics,
- vulnerability remediation metrics,
- observability coverage metrics.

The AI should avoid proposing metrics without:

- a purpose,
- a measurement definition,
- and a warning about misuse where appropriate.

## Architecture posture the AI should assume

The references support the idea that architecture should be described through explicit decisions, views, and tradeoffs.

The AI should therefore:

- make architectural assumptions visible,
- record decisions explicitly,
- identify tradeoffs,
- define boundaries,
- and choose patterns based on context instead of fashion.

Patterns mentioned in the references include:

- modular monolith,
- microservices,
- event-driven architecture,
- hexagonal architecture,
- clean architecture.

The AI should treat these as context-dependent options.

For ArchSpec, the default bias should be toward the simplest architecture that preserves clear boundaries and future evolution.

## Documentation posture the AI should assume

The references strongly imply that good documentation is structured, versioned, and tied to decisions or verification.

The AI should prefer documentation that is:

- purposeful,
- scoped,
- linked to ownership,
- versioned,
- reviewable,
- and, where possible, machine-checkable.

The AI should avoid creating large narrative documents that have no obvious role in the lifecycle.

## Deliverable mindset

The references collectively reinforce that formal engineering requires explicit artifacts.

The AI should assume a mature delivery effort usually needs deliverables such as:

- requirements catalogs,
- architecture descriptions,
- technical specifications,
- data models,
- ADRs,
- test strategy and evidence,
- implementation plans,
- migration plans,
- release and operations documentation,
- and change impact records.

If a request touches software lifecycle structure, the AI should think in deliverables, not only tasks.

## AI-specific heuristics derived from the references

### Prefer structured outputs

The references explicitly connect SDD to AI workflows through structured outputs and machine-readable constraints.

The AI should prefer:

- schemas,
- explicit field structures,
- checklists,
- contracts,
- enumerated assumptions,
- and verifiable criteria.

### Never let vague prompts become hidden business rules

The references repeatedly warn that LLMs fill gaps when requirements are underspecified.

The AI should therefore:

- surface ambiguity,
- avoid inventing hidden business rules,
- push missing intent back into manifests,
- and ask for clarification only when the risk is material and cannot be resolved responsibly.

### Translate intent into layers

A recurring pattern in the references is that good spec-driven systems separate:

- intent,
- design,
- tasks,
- implementation,
- verification.

The AI should therefore translate requests into the correct layer instead of jumping directly into code.

### Fail closed where possible

The references around agent-driven SDD emphasize controls that prevent low-quality or drifting outputs from silently passing through automation.

The AI should favor workflows where:

- invalid specs fail validation,
- incompatible contracts fail CI,
- generated artifacts are reviewable,
- and ambiguous AI output does not silently become production truth.

## Risks the AI should actively watch for

The references repeatedly highlight these risk patterns:

- ambiguous requirements,
- spec drift,
- over-specification,
- hidden complexity in the meta-model,
- tool lock-in,
- false confidence from well-formatted specs,
- architecture overreach,
- governance gaps,
- brittle pipelines,
- supply chain risk,
- metrics misuse.

When the AI notices one of these, it should say so explicitly and propose a mitigation.

## Mitigation patterns the AI should favor

Across the references, the most defensible mitigation patterns are:

- iterative refinement,
- examples and acceptance criteria,
- architecture and product separation,
- lightweight but explicit governance,
- CI-based validation,
- contract testing,
- schema-based verification,
- ADRs for meaningful tradeoffs,
- traceability,
- measurable quality evidence,
- and keeping the framework tool-agnostic where possible.

## Practical assumptions for ArchSpec-specific work

When working in this repository, the AI should usually assume:

- the framework should remain reusable across multiple products,
- the architecture manifest should remain domain-agnostic,
- product specs may vary by business language and domain,
- the active product is only one validation case,
- reusable capabilities belong to the scaffolding layer,
- and product-specific behavior belongs to the product layer.

## What the AI should avoid

The references imply several anti-patterns the AI should avoid:

- treating the codebase as the only source of truth,
- mixing stack decisions into product definitions without reason,
- mixing product rules into reusable architecture,
- generating diagrams or docs with no regeneration path,
- assuming a tool is mandatory just because it is popular,
- replacing explicit review with AI confidence,
- and defining a meta-model so large that it becomes its own unmanageable language.

## Working heuristics for future development

When the AI needs to make a decision under uncertainty, these heuristics should apply:

- prefer explicit contracts over implied behavior,
- prefer smaller composable manifests over one overloaded universal file,
- prefer reusable capability modules over one-off implementation shortcuts,
- prefer platform-independent intent before platform-specific realization,
- prefer evidence-producing workflows over narrative-only workflows,
- prefer simple architecture with clean boundaries before distributed complexity,
- prefer enforcement mechanisms whenever a spec is expected to stay authoritative.

## Relationship to raw `deep-research-reports/`

`deep-research-reports/` should still be treated as the long-form research archive.

This file is the operational synthesis.

If future reference documents are added, `REFERENCES.md` should be updated so the AI can keep using a stable, curated methodological baseline instead of re-parsing the full archive every time.

## In short

The references establish that ArchSpec should be developed as:

- a spec-driven framework,
- grounded in formal software engineering thinking,
- explicit about lifecycle and deliverables,
- careful about quality, security, and governance,
- compatible with AI-assisted development,
- and strict about separating reusable architecture from product-specific intent.
