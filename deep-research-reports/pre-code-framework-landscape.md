# Pre-Code Framework Landscape for Spec-Centric Development

## Purpose

This document is an AI-readable knowledge-base entry about frameworks and tool families that operate before code and treat higher-level definitions as the primary source of truth.

It preserves the ideas of the original research document while reorganizing them into a factual, update-friendly reference format.

This file is intended to be:

- a manually refreshable state-of-the-art note,
- a map of relevant precedent families,
- and a decision-support reference for frameworks such as ArchSpec.

This file is not intended to be:

- the active framework contract,
- the active product specification,
- or a commitment to one tool or vendor.

## Executive Summary

A pre-code framework treats code, folders, diagrams, and documentation as derivable outputs from higher-level definitions rather than as the original source of truth.

The core pattern described by this document is:

- a project is defined first through agent guidance and structured specifications,
- platform choices such as Python are treated as realizations of the definition rather than as the starting point,
- and multiple products can be derived from the same project-level intent, including both code and non-code artifacts.

This is best understood as a reaction against unstructured AI-assisted coding, sometimes described as "vibe coding," where a model is guided through prompts without enough durable structure.

The important claim is not that this idea is unprecedented. The important claim is that existing precedent families usually solve only one part of the problem:

- platform-independent modeling,
- reusable production assets,
- repo scaffolding,
- organizational golden paths,
- agent guidance files,
- or spec-driven workflows.

The opportunity for a framework like ArchSpec lies in composing these strands into one coherent contract.

## Core Reading Frame

When analyzing frameworks of this kind, the most useful question is:

What is treated as the authoritative definition of the system?

In a pre-code, spec-centric framework, the intended answer is:

- agent guidance,
- project composition,
- platform-independent intent,
- and structured product-level specifications.

Code becomes a realization of those definitions rather than the primary place where intent is discovered.

## Major Precedent Families

### 1. Model-Driven Engineering and Platform Independence

Model-Driven Architecture and related model-driven approaches separate stable system intent from platform-specific realization.

Key contribution:

- the idea that platform-independent models can be transformed into platform-specific implementations.

Why it matters here:

- it supports the claim that "Python" or any other stack should be treated as a mapping target rather than as the original design language.

Limitation:

- traditional model-driven approaches often focus more on transformation theory and metamodels than on agent workflows, repository conventions, or mixed human-AI collaboration.

### 2. Software Factories and Reusable Production Assets

Software factories treat a family of systems as something that can be produced systematically through:

- reusable assets,
- templates,
- patterns,
- guidance,
- and tooling.

Key contribution:

- the idea that the way software is produced can itself be captured as an explicit reusable system.

Why it matters here:

- it is a direct precursor to the claim that a framework can encode how a project should be structured before project-specific code exists.

Limitation:

- software factory literature often assumes a more centralized engineering process and does not necessarily place agent-readable contracts at the center.

### 3. Scaffolding and Template Systems

Template tools such as Cookiecutter and Copier generate repository structures from parameterized templates.

Key contribution:

- they prove that teams value repeatable project bootstrap and reusable repo structure.

Why it matters here:

- they are practical mechanisms for turning a spec or parameter set into a starting repository.

Limitation:

- classic scaffolding is usually template to code, not universal spec to multiple derived products.

### 4. Platform Engineering and Golden Paths

Portal systems such as Backstage templates define organizational golden paths for:

- repo creation,
- standard service setup,
- variable injection,
- and platform-approved patterns.

Key contribution:

- they operationalize standardization and onboarding at scale.

Why it matters here:

- they show how a spec-driven workflow can be embedded into organizational delivery practice.

Limitation:

- they are usually oriented around organizational workflow and service onboarding rather than around a general project spec acting as a universal source of truth.

### 5. Agent Instruction Files

`AGENTS.md` has become an emerging ecosystem convention for giving coding agents project-specific instructions, constraints, and context.

Key contribution:

- a portable, repository-local artifact for agent behavior control.

Why it matters here:

- it makes the "agent guidance contract" a practical, interoperable part of a framework design.

Important ecosystem fact:

- multiple agent ecosystems now recognize or document `AGENTS.md` as a meaningful project-level instruction file.

Limitation:

- `AGENTS.md` alone does not define domain intent, platform-independent architecture, or derived artifact rules.

### 6. Spec-Driven Development Toolkits

Recent toolkits such as GitHub Spec Kit and OpenSpec organize software work around:

- structured specs,
- plans,
- tasks,
- deltas,
- and staged implementation.

Key contribution:

- they turn pre-code specification into an explicit engineering workflow.

Why it matters here:

- they are the closest modern precedent for a workflow in which intent is formalized before implementation.

Limitation:

- many of these approaches focus on spec-plan-task-code workflow rather than on one project-level contract that can derive multiple product outputs such as code, diagrams, and documents.

### 7. Specialized DSLs and Generators

Text-based definitions for ER diagrams, APIs, schemas, and migrations already exist through tools such as:

- Mermaid,
- DBML,
- PlantUML,
- OpenAPI,
- AsyncAPI,
- and schema-driven data tools.

Key contribution:

- they prove that many important artifacts can already be described as versionable text and generated from structured definitions.

Why it matters here:

- they are strong candidates for the "product engines" that a higher-level framework can orchestrate.

Limitation:

- they solve artifact-specific problems rather than serving as a universal project definition layer.

## Comparative View

| Family | Main strength | What it contributes to a pre-code framework | What it does not solve by itself |
|---|---|---|---|
| Model-driven engineering | Platform-independent intent | Stable intent versus stack realization | Agent guidance and modern workflow orchestration |
| Software factories | Reusable production logic | Industrialization of system families | Lightweight repo-native spec workflows |
| Template scaffolding | Fast project bootstrap | Repeatable repo creation | Multiproduct derivation from one authoritative spec |
| Platform engineering and golden paths | Organizational standardization | Standard onboarding and service templates | Project-level universal intent modeling |
| `AGENTS.md` | Agent interoperability | Durable agent instructions in the repo | Product semantics and derivation rules |
| Spec-driven toolkits | Spec-first workflow | Structured spec to plan to task flow | Unified multi-artifact project composition |
| DSLs and generators | Derivable artifact production | Concrete outputs such as diagrams or API contracts | Cross-artifact orchestration and governance |

## What Can Be Distinctive About a Framework Like ArchSpec

If a framework of this kind is well-defined, its main differentiators are likely to be:

- one unifying project specification rather than isolated templates or markdown-only specs,
- multiproduct derivation as a first-class concept,
- support for non-code outputs such as ER diagrams and architectural deliverables from day zero,
- platform mappings where Python or another stack is only a realization target,
- and a framework-first posture where the contract remains valid even if the underlying generators or tools change.

This matters because otherwise the framework risks collapsing into:

- another scaffolding template,
- another spec-plan-task toolkit,
- or another YAML wrapper around existing tooling.

## Recommended Design Pattern for This Category of Framework

The strongest design pattern suggested by the landscape is to define contracts rather than a single mandatory tool.

### 1. Instruction Contract

Use `AGENTS.md` as the operational onboarding contract for coding agents.

Typical responsibilities:

- execution boundaries,
- coding conventions,
- review expectations,
- repository navigation rules,
- and non-negotiable constraints.

### 2. Intent Contract

Use a project-level structured file such as `project-spec.yaml` as the platform-independent description of:

- domain intent,
- use cases,
- data concepts,
- interface expectations,
- constraints,
- and target platform mappings.

### 3. Product Catalog

Declare explicitly which products can be derived from the project definition, for example:

- repo scaffolding,
- ER diagrams,
- API contracts,
- migrations,
- documentation,
- tests,
- ADRs,
- or other delivery artifacts.

Each product should declare its preferred derivation engine where relevant.

### 4. Automation as an Optional Layer

The framework should work in both modes:

- light mode with conventions and structured files only,
- and automated mode with validators, generators, or plugins.

This keeps the framework durable even when tooling changes.

### 5. Separation of Intent, Design, and Work Execution

A useful split is:

- what and why:
  functional intent, scenarios, acceptance criteria, domain language,
- how:
  technical plan, architecture, constraints, mappings,
- executable work:
  tasks, slices, validation commands, and implementation checkpoints.

This separation is compatible with modern spec-driven workflows while remaining tool-agnostic.

## Practical Product Engines That Fit Beneath This Framework

### ER and Data Modeling Outputs

Useful text-first options include:

- Mermaid ER diagrams,
- DBML,
- PlantUML,
- or database-derived documentation tools when a real schema already exists.

For a pre-code framework, text-first tools are usually the best fit because the definition can exist in the repository before a live database exists.

### Interface and Contract Outputs

Useful options include:

- OpenAPI for HTTP contracts,
- AsyncAPI for event-driven contracts,
- JSON Schema for data structures,
- and code/document generators that derive clients, stubs, docs, or validation artifacts.

### Project Bootstrap Outputs

Useful options include:

- Cookiecutter,
- Copier,
- Backstage templates,
- or custom generators aligned to the framework's own manifest contracts.

## Risks, Limits, and Success Criteria

### Structural Risks

- Ambiguity:
  LLMs fill gaps aggressively. Weak specs force guesswork.

- Spec-implementation drift:
  a spec becomes dead documentation unless the workflow defines how it stays authoritative.

- Project-spec overgrowth:
  the more universal the project spec becomes, the more it risks turning into a complex DSL with expensive semantics.

- Tool dependency:
  tying the framework too tightly to one generator or portal reduces long-term durability.

### Practical Success Criteria

A successful framework of this type should be able to:

- interoperate cleanly with `AGENTS.md`,
- treat the spec as a living source of truth rather than a one-time bootstrap file,
- derive at least some high-value products from structured definitions,
- and support platform mapping where technology choices remain realizations instead of foundational identity.

## Final Reading Frame for AI Systems

The safest high-level interpretation of this landscape is:

- the idea is real and has strong precedent,
- no single existing family solves the full problem alone,
- the strongest opportunity lies in composing agent guidance, structured project intent, and multiproduct derivation,
- and the main design challenge is to define a durable contract without turning the project spec into an unbounded DSL.

## Reference Basis to Refresh Manually

When refreshing this file against the state of the art, prioritize checking developments in:

- model-driven engineering and MDA,
- software factories,
- template and scaffolding systems such as Cookiecutter and Copier,
- platform engineering systems such as Backstage,
- `AGENTS.md` ecosystem adoption,
- GitHub Spec Kit and related spec-driven toolkits,
- text-based diagram DSLs such as Mermaid, DBML, and PlantUML,
- OpenAPI and AsyncAPI ecosystems,
- and platform-specific starter templates for major stacks.
