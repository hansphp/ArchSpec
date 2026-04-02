# ArchSpec Delivery Lifecycle Roadmap

This document defines a baseline delivery lifecycle for building applications with ArchSpec.

It has two goals:

- define a clear lifecycle for using this scaffolding,
- enumerate the formal deliverables expected from a well-documented software solution.

This roadmap is inspired by TOGAF and adapted to practical software architecture and software engineering work.

It is not a verbatim TOGAF reproduction.

It is an ArchSpec-oriented operating model that translates TOGAF ADM ideas, architecture content concepts, governance practices, and example deliverables into a concrete delivery checklist for real software projects.

## Official reference basis

This roadmap was derived from official TOGAF material, especially:

- The TOGAF Standard, 10th Edition, which separates the fundamental content into core concepts, the Architecture Development Method, ADM techniques, applying the ADM, architecture content, and enterprise architecture capability and governance.
- The TOGAF Standard, 10th Edition Template Deliverables, which provides example deliverables across the Preliminary Phase and Phases A through H.
- The TOGAF Standards and TOGAF Library pages, which position the standard, guides, templates, and reference materials as the official ecosystem around TOGAF.

Reference links:

- https://publications.opengroup.org/c220
- https://publications.opengroup.org/togaf-library/i094
- https://publications.opengroup.org/standards/togaf

## Why this roadmap exists

ArchSpec separates:

- workspace composition,
- reusable architecture,
- product definition.

That separation is powerful, but it also needs a repeatable lifecycle so teams know:

- what to define first,
- what to iterate on,
- what to test,
- what to deliver,
- when a phase is complete,
- and which artifacts prove that the work is actually done.

This document is that lifecycle.

## TOGAF alignment

This roadmap is aligned to TOGAF in the following way:

- Preliminary Phase becomes architecture capability setup and project initiation.
- Phase A becomes architecture vision and scoped engagement setup.
- Phases B, C, and D become structured definition cycles for business, application, data, and technology architecture.
- Phases E and F become delivery planning, migration planning, governance setup, and work packaging.
- Phase G becomes governed implementation and compliance verification.
- Phase H becomes change management and controlled evolution.
- Requirements Management is continuous across the entire lifecycle.

In ArchSpec terms:

- `project-spec.yaml` anchors composition and active context,
- `scaffold/architecture-manifest.yaml` anchors reusable technical architecture,
- `products/<slug>/product-spec.yaml` anchors business and product definition,
- delivery work is derived from those manifests.

## Lifecycle overview

The baseline lifecycle has eight phases:

0. Architecture Capability Setup
1. Vision and Requirements Framing
2. Definition Cycles
3. Architecture Consolidation and Technical Specification
4. Implementation and Migration Planning
5. Engineering Delivery Cycles
6. Verification, Acceptance, and Release Readiness
7. Release, Handover, and Change Evolution

Requirements Management is continuous across all phases.

## Phase map

| ArchSpec Phase | TOGAF Anchor | Primary Outcome |
|---|---|---|
| 0. Architecture Capability Setup | Preliminary | Tailored working model, governance, repository, principles |
| 1. Vision and Requirements Framing | Phase A + Requirements Management | Shared scope, value case, stakeholders, initial requirements |
| 2. Definition Cycles | Phases B, C, D | Business, information, application, and technology architecture defined iteratively |
| 3. Architecture Consolidation and Technical Specification | B-D consolidation | Integrated target architecture and application technical specification |
| 4. Implementation and Migration Planning | Phases E, F | Work packages, roadmap, migration plan, governance model |
| 5. Engineering Delivery Cycles | Phase G | Implemented solution increments under architecture governance |
| 6. Verification, Acceptance, and Release Readiness | Phase G + cross-cutting QA | Tested, compliant, accepted release candidate |
| 7. Release, Handover, and Change Evolution | Phase H | Released product, operational handover, controlled change backlog |

## Lifecycle principles

- Manifest-first before code-first.
- Architecture and product remain separate.
- Requirements are managed continuously, not only at the start.
- Definition work and engineering work are traceable through deliverables.
- Every phase has entry criteria, exit criteria, and observable artifacts.
- Testing is continuous, but formal acceptance has explicit gates.
- Release readiness is a documented decision, not a feeling.
- Architecture change is governed, not improvised.

## Slug bootstrap convention

Before Phase 0 can progress, a new product engagement must resolve the project slug.

Canonical first prompt:

```text
Create the project "helpdesk-lite" as a new project.
```

That prompt should establish the active product context, map the resolved slug to `project-spec.yaml`, and identify `products/<slug>/product-spec.yaml` as the target product manifest before any deeper definition work begins.

## How to use this document

Use this roadmap in one of two ways:

- as the complete lifecycle for a new product built with ArchSpec,
- or as a checklist to assess how mature and complete an existing product definition is.

Recommended use:

1. start at Phase 0 and tailor the lifecycle,
2. decide which deliverables are mandatory for the specific engagement,
3. create and track the deliverables,
4. gate each phase based on evidence,
5. carry unresolved gaps forward explicitly instead of implicitly.

## Continuous lane: Requirements Management

Requirements Management is not a single phase.

It is active throughout the entire lifecycle.

That means the team should maintain, at all times:

- a requirements catalog,
- change requests,
- traceability between requirements and deliverables,
- impact analysis for requirement changes,
- and explicit decisions about accepted, deferred, or rejected requirements.

Minimum checklist:

- [ ] Requirements are uniquely identified.
- [ ] Functional and non-functional requirements are separated.
- [ ] Requirements are linked to business goals or drivers.
- [ ] Requirements are linked to product capabilities or architecture concerns.
- [ ] Requirement changes are impact-assessed before implementation.
- [ ] Acceptance criteria exist for critical requirements.

## Phase 0. Architecture Capability Setup

### Purpose

Create the operating conditions for a disciplined architecture and delivery effort.

This phase prepares the team, repository, rules, governance, and baseline architecture posture before detailed product definition begins.

### Typical activities

- define architecture principles,
- define business principles, goals, and drivers,
- establish the architecture repository structure,
- tailor the framework for the engagement,
- define ownership and governance roles,
- resolve and normalize the project slug from the project-creation prompt,
- confirm the active architecture manifest and product context,
- define working agreements for documentation, review, and decision-making.

### Checklist

- [ ] Architecture principles are defined.
- [ ] Business principles, goals, and drivers are documented.
- [ ] The architecture repository structure is agreed.
- [ ] Governance roles and decision owners are identified.
- [ ] The working architecture framework is tailored for the engagement.
- [ ] The project slug is defined and mapped to the active product context.
- [ ] The active architecture manifest is confirmed.
- [ ] The active product context is confirmed.
- [ ] Decision logging is defined.
- [ ] Artifact naming and versioning conventions are defined.
- [ ] Communication and review cadence is defined.

### Exit criteria

- The project knows how architecture decisions will be made.
- The team knows where artifacts live.
- The team knows which slug identifies the active product context.
- The team knows which manifests are authoritative.
- The team can begin structured definition work without ambiguity.

### Key deliverables

- Architecture Principles
- Business Principles, Goals, and Drivers
- Tailored Architecture Framework
- Architecture Repository Index
- Organizational Model for Architecture Work
- Architecture Governance Model
- Active Product Slug Registration
- Decision Log or ADR Policy
- Initial Request for Architecture Work

## Phase 1. Vision and Requirements Framing

### Purpose

Define why the application exists, who it serves, what value it must create, and what the engagement is expected to deliver.

This phase should produce enough clarity to scope the architecture and begin iterative definition cycles.

### Typical activities

- identify stakeholders,
- define the problem statement,
- define business outcomes and success metrics,
- define scope and non-scope,
- identify constraints and assumptions,
- capture initial requirements,
- define the architecture vision,
- define the statement of architecture work,
- define the communications approach.

### Checklist

- [ ] Stakeholders are identified and categorized.
- [ ] Business problem and opportunity are written clearly.
- [ ] Goals, drivers, and success criteria are documented.
- [ ] In-scope and out-of-scope boundaries are explicit.
- [ ] Constraints, assumptions, and dependencies are documented.
- [ ] Initial requirements are captured.
- [ ] Non-functional expectations are captured.
- [ ] The architecture vision is approved.
- [ ] The statement of architecture work is approved.
- [ ] A communications plan exists.

### Exit criteria

- Stakeholders share the same intent.
- The engagement has clear scope.
- Initial requirements are sufficient to start structured architecture definition.
- The team has authority to proceed.

### Key deliverables

- Stakeholder Map
- Problem Statement
- Scope Definition
- Goals, Drivers, and Success Metrics
- Constraints and Assumptions Log
- Initial Requirements Catalog
- Architecture Vision
- Capability Assessment
- Communications Plan
- Statement of Architecture Work

## Phase 2. Definition Cycles

### Purpose

Run the iterative cycles that define the target solution across business, data, application, and technology perspectives.

This is where most architecture thinking happens.

These cycles are not strictly linear.

They are iterative and may repeat until the architecture is coherent enough for engineering and planning.

### Structure of the definition cycles

Phase 2 is divided into four recurring cycles:

1. Business and product definition cycle
2. Information and data definition cycle
3. Application and integration definition cycle
4. Technology and operational definition cycle

Each cycle should refine both:

- the relevant manifests,
- and the supporting architecture artifacts.

### Cycle 2.1 Business and product definition

Focus:

- business capabilities,
- user workflows,
- domain model,
- business rules,
- KPIs,
- reports,
- operating scope.

Checklist:

- [ ] Product purpose is explicit.
- [ ] Business capabilities are defined.
- [ ] User or operational workflows are documented.
- [ ] Domain entities and relationships are modeled.
- [ ] Business rules are explicit.
- [ ] KPIs and formulas are explicit.
- [ ] Reports, exports, and imports are listed.
- [ ] Product boundaries and interfaces are identified.

Key deliverables:

- Product Specification
- Business Capability Map
- Business Process or Workflow Diagrams
- Domain Model
- Business Rules Catalog
- KPI Catalog
- Product Scope Model
- Report Catalog

### Cycle 2.2 Information and data definition

Focus:

- conceptual, logical, and physical data shape,
- ownership of data,
- lifecycle of data,
- master data,
- quality rules,
- retention and migration implications.

Checklist:

- [ ] Conceptual data entities are defined.
- [ ] Logical data relationships are defined.
- [ ] Physical persistence strategy is defined.
- [ ] Data ownership is assigned.
- [ ] Data quality rules are defined.
- [ ] Data classification is considered.
- [ ] Retention and archival needs are identified.
- [ ] Migration implications are identified.

Key deliverables:

- Conceptual Data Model
- Logical Data Model
- Physical Data Model
- Data Dictionary
- Entity Relationship Diagram
- Data Lifecycle Matrix
- Data Quality Rules
- Data Classification Matrix
- Data Migration Constraints

### Cycle 2.3 Application and integration definition

Focus:

- application services,
- API boundaries,
- component decomposition,
- integration patterns,
- event flows,
- user-facing modules,
- contract definitions.

Checklist:

- [ ] Application modules are identified.
- [ ] Service responsibilities are defined.
- [ ] API boundaries are defined.
- [ ] Integration points are defined.
- [ ] Contract types are selected.
- [ ] Error handling and state transitions are considered.
- [ ] UI modules are aligned with workflows.
- [ ] Reusable architecture capabilities are mapped to product needs.

Key deliverables:

- Application Architecture Diagram
- Service Catalog
- Interface Catalog
- API Specification or OpenAPI Contract
- Integration Architecture
- Event Catalog, if applicable
- UI Module Map
- Component Interaction Diagrams

### Cycle 2.4 Technology and operational definition

Focus:

- runtime,
- environments,
- deployment topology,
- security,
- observability,
- backup and recovery,
- performance and resilience posture.

Checklist:

- [ ] Technology stack is confirmed.
- [ ] Environment model is defined.
- [ ] Deployment topology is defined.
- [ ] Security controls are identified.
- [ ] Logging and monitoring needs are defined.
- [ ] Backup and recovery needs are defined.
- [ ] Performance expectations are defined.
- [ ] Availability and resilience expectations are defined.

Key deliverables:

- Technology Architecture
- Environment Topology
- Deployment Architecture
- Security Architecture
- Identity and Access Model
- Observability Plan
- Backup and Recovery Plan
- Performance and Capacity Notes

### Exit criteria for Phase 2

- The business, data, application, and technology definitions are mutually coherent.
- Major architectural risks are visible.
- The product and architecture manifests reflect the agreed architecture.
- The team can consolidate the solution into a formal technical specification.

### Phase 2 key deliverables

- Architecture Requirements Specification
- Architecture Roadmap, first version
- Business Architecture Package
- Data Architecture Package
- Application Architecture Package
- Technology Architecture Package

## Phase 3. Architecture Consolidation and Technical Specification

### Purpose

Convert the outputs of the definition cycles into a single integrated solution package that engineering can implement without guessing.

This phase turns architecture into a complete technical baseline.

### Typical activities

- consolidate architecture views,
- resolve contradictions between definition cycles,
- formalize interfaces and constraints,
- define quality attributes,
- define acceptance criteria,
- define the application technical specification,
- define traceability from requirements to solution elements.

### Checklist

- [ ] Architecture views are consistent with one another.
- [ ] Open contradictions are resolved or explicitly accepted.
- [ ] Quality attributes are documented.
- [ ] Technical constraints are documented.
- [ ] Acceptance criteria exist for major capabilities.
- [ ] Requirements traceability is defined.
- [ ] The application technical specification is complete.
- [ ] Security, data, and operational requirements are represented.

### Exit criteria

- Engineering can start with minimal ambiguity.
- Acceptance expectations are visible.
- Solution boundaries and contracts are stable enough to plan delivery.

### Key deliverables

- Architecture Definition Document
- Application Technical Specification
- Solution Design Package
- Requirements Traceability Matrix
- Quality Attribute Scenarios
- Acceptance Criteria Matrix
- Architecture Decision Records
- Risk Register, updated

## Phase 4. Implementation and Migration Planning

### Purpose

Turn the target architecture into a delivery plan.

This phase organizes work into packages, releases, dependencies, migration steps, and governance controls.

### Typical activities

- identify work packages,
- sequence releases,
- define implementation strategy,
- define migration strategy,
- define transition architectures if needed,
- establish governance checkpoints,
- define architecture contract and compliance approach.

### Checklist

- [ ] Work packages are defined.
- [ ] Dependencies are mapped.
- [ ] Release slices are defined.
- [ ] Migration strategy is defined.
- [ ] Transition states are documented if needed.
- [ ] Governance review points are defined.
- [ ] Architecture compliance criteria are defined.
- [ ] Implementation ownership is assigned.
- [ ] Delivery risks are assessed.

### Exit criteria

- The team knows what to build first.
- The roadmap is sequenced and realistic.
- Migration and rollout risk are visible.
- Governance and compliance expectations are explicit.

### Key deliverables

- Implementation and Migration Plan
- Architecture Roadmap, approved version
- Work Package Model
- Release Plan
- Transition Architecture Definitions, if needed
- Architecture Building Blocks
- Solution Building Blocks, planned
- Architecture Contract
- Implementation Governance Model
- Dependency Map

## Phase 5. Engineering Delivery Cycles

### Purpose

Implement the solution incrementally while keeping architecture and product definitions in sync.

This phase covers actual engineering cycles such as sprint-based delivery, milestone-based delivery, or hybrid execution.

### Typical activities

- implement prioritized work packages,
- produce code and runtime assets,
- create migrations,
- create reports and templates,
- update API contracts,
- review architecture compliance,
- update traceability and decisions.

### Checklist

- [ ] Each implementation increment is traceable to requirements.
- [ ] Each increment is traceable to architecture or product artifacts.
- [ ] Code changes reflect manifest ownership.
- [ ] Database migrations are versioned and reviewed.
- [ ] API contracts are implemented and versioned.
- [ ] Runtime configuration is explicit.
- [ ] Architecture decisions are recorded when new tradeoffs appear.
- [ ] Compliance reviews happen at agreed checkpoints.

### Exit criteria

- A release candidate exists.
- The implementation is aligned with the agreed architecture.
- Engineering artifacts are sufficiently complete for formal validation.

### Key deliverables

- Source Code Baseline
- Database Migration Scripts
- API Implementations
- Frontend Implementations
- Report Templates
- Import and Export Templates
- Runtime Configuration
- CI/CD Definitions
- Architecture Compliance Review Notes
- Updated ADR Log

## Phase 6. Verification, Acceptance, and Release Readiness

### Purpose

Prove that the solution works, is compliant, is operable, and is acceptable to stakeholders.

Testing is continuous throughout the lifecycle, but this phase is where evidence is consolidated into a formal release decision.

### Test cycle structure

The baseline test cycles should cover:

1. specification quality review,
2. design review,
3. unit testing,
4. integration testing,
5. system or end-to-end testing,
6. security and non-functional testing,
7. user acceptance testing,
8. release readiness review.

### Checklist

- [ ] Specifications were reviewed for completeness and consistency.
- [ ] Architecture and design were reviewed.
- [ ] Unit tests exist for critical logic.
- [ ] Integration tests cover key flows.
- [ ] End-to-end or system tests cover core journeys.
- [ ] Performance testing was performed as needed.
- [ ] Security testing was performed as needed.
- [ ] Data migration testing was performed if relevant.
- [ ] UAT evidence exists.
- [ ] Operational readiness was reviewed.
- [ ] Known defects are triaged and dispositioned.

### Exit criteria

- Stakeholders accept the release candidate.
- Quality evidence is sufficient for release.
- Risks and defects are understood and dispositioned.
- The solution is operationally ready.

### Key deliverables

- Test Strategy
- Test Plan
- Test Cases
- Test Automation Suites
- Test Execution Results
- Defect Log
- Security Assessment Report
- Performance Test Report
- Data Migration Validation Report
- UAT Sign-off
- Release Readiness Assessment
- Compliance Assessment

## Phase 7. Release, Handover, and Change Evolution

### Purpose

Move the solution into use, hand it over responsibly, and manage change in a controlled way.

This phase closes the release loop and opens the next change loop.

### Typical activities

- deploy to the target environment,
- complete operational handover,
- publish release notes,
- validate monitoring and support procedures,
- register post-release issues and changes,
- assess requirement impacts for incoming changes.

### Checklist

- [ ] Deployment steps are documented and executed.
- [ ] Release notes are prepared.
- [ ] Runbooks are complete.
- [ ] Support ownership is assigned.
- [ ] Monitoring and alerting are active.
- [ ] Backup and recovery procedures are confirmed.
- [ ] Post-release validation is completed.
- [ ] Change requests are logged for the next iteration.
- [ ] Requirement impact assessments are performed for approved changes.

### Exit criteria

- The solution is live or formally handed over.
- Operations can support the solution.
- The next change cycle can start from a controlled baseline.

### Key deliverables

- Deployment Guide
- Operations Runbook
- Support Model
- Monitoring and Alerting Configuration
- Release Notes
- Operational Handover Package
- Change Request Log
- Requirements Impact Assessment
- Post-Implementation Review

## Master deliverables catalog

The lists below define the full formal deliverable inventory for a well-documented software solution.

Not every engagement will need every item, but this is the baseline catalog ArchSpec should be able to support.

### A. Governance and architecture management deliverables

- [ ] Architecture Principles
- [ ] Business Principles, Goals, and Drivers
- [ ] Tailored Architecture Framework
- [ ] Architecture Repository Index
- [ ] Organizational Model for Architecture
- [ ] Request for Architecture Work
- [ ] Statement of Architecture Work
- [ ] Communications Plan
- [ ] Architecture Governance Model
- [ ] Architecture Contract
- [ ] Architecture Compliance Assessment
- [ ] Architecture Decision Records
- [ ] Exception and Waiver Log

### B. Strategy, scope, and business deliverables

- [ ] Problem Statement
- [ ] Vision Statement
- [ ] Business Outcomes and Success Metrics
- [ ] Scope and Context Definition
- [ ] Stakeholder Map
- [ ] Business Capability Map
- [ ] Business Scenarios
- [ ] Process Models or Workflow Diagrams
- [ ] Personas or Operating Roles, if relevant
- [ ] KPI Catalog
- [ ] Business Rules Catalog
- [ ] Benefits and Value Case

### C. Requirements deliverables

- [ ] Requirements Catalog
- [ ] Functional Requirements Specification
- [ ] Non-Functional Requirements Specification
- [ ] Constraints and Assumptions Log
- [ ] Dependency Log
- [ ] Acceptance Criteria Matrix
- [ ] Requirements Traceability Matrix
- [ ] Requirements Impact Assessment
- [ ] Change Request Register

### D. Product and domain deliverables

- [ ] Product Specification
- [ ] Product Scope Model
- [ ] Domain Model
- [ ] Ubiquitous Language or Business Glossary
- [ ] Use Case Catalog
- [ ] User Journey Map, if relevant
- [ ] Report Catalog
- [ ] Import and Export Catalog
- [ ] Product Backlog or Feature Breakdown

### E. Data architecture deliverables

- [ ] Conceptual Data Model
- [ ] Logical Data Model
- [ ] Physical Data Model
- [ ] Entity Relationship Diagram
- [ ] Data Dictionary
- [ ] Data Ownership Matrix
- [ ] Data Quality Rules
- [ ] Data Classification Matrix
- [ ] Master Data Definitions, if relevant
- [ ] Retention and Archival Rules
- [ ] Data Migration Strategy

### F. Application and integration deliverables

- [ ] Application Architecture Diagram
- [ ] Service Catalog
- [ ] Interface Catalog
- [ ] API Specification
- [ ] Event Catalog, if relevant
- [ ] Integration Architecture
- [ ] Component Decomposition
- [ ] Sequence or Interaction Diagrams
- [ ] UI Module Map
- [ ] Frontend Navigation Model

### G. Technology and operations architecture deliverables

- [ ] Technology Architecture
- [ ] Runtime Profile
- [ ] Environment Matrix
- [ ] Deployment Topology
- [ ] Infrastructure Model
- [ ] Security Architecture
- [ ] Identity and Access Model
- [ ] Observability Plan
- [ ] Backup and Recovery Plan
- [ ] Capacity and Performance Plan
- [ ] Availability and Resilience Plan

### H. Technical engineering deliverables

- [ ] Application Technical Specification
- [ ] Solution Design Package
- [ ] Coding Standards
- [ ] Branching and Versioning Strategy
- [ ] Build and Packaging Strategy
- [ ] CI/CD Pipeline Definition
- [ ] Configuration Management Strategy
- [ ] Database Migration Scripts
- [ ] Seed Data Strategy
- [ ] Environment Configuration Templates

### I. Planning and implementation deliverables

- [ ] Architecture Roadmap
- [ ] Implementation and Migration Plan
- [ ] Work Package Breakdown
- [ ] Release Plan
- [ ] Transition Architecture Definitions, if relevant
- [ ] Delivery Milestone Plan
- [ ] Dependency Map
- [ ] Resource and Ownership Plan
- [ ] Risk Register
- [ ] Issue Log

### J. Testing and quality deliverables

- [ ] Test Strategy
- [ ] Test Plan
- [ ] Test Cases
- [ ] Unit Test Suite
- [ ] Integration Test Suite
- [ ] End-to-End Test Suite
- [ ] Test Data Strategy
- [ ] Test Execution Report
- [ ] Defect Log
- [ ] Security Test Report
- [ ] Performance Test Report
- [ ] Accessibility Review, if relevant
- [ ] UAT Sign-off
- [ ] Release Readiness Assessment

### K. Release and operations deliverables

- [ ] Deployment Guide
- [ ] Release Notes
- [ ] Runbook
- [ ] Support Model
- [ ] Monitoring and Alerting Configuration
- [ ] Incident Response Guide
- [ ] Backup and Restore Procedure
- [ ] Operational Handover Package
- [ ] SLA, SLO, or support commitments, if relevant
- [ ] Post-Implementation Review

## Mandatory minimum deliverable set

If the team needs a practical minimum for a formal but not overly heavy engagement, start with the following mandatory set:

- [ ] Architecture Principles
- [ ] Scope and Context Definition
- [ ] Stakeholder Map
- [ ] Requirements Catalog
- [ ] Non-Functional Requirements Specification
- [ ] Product Specification
- [ ] Domain Model
- [ ] Business Rules Catalog
- [ ] Architecture Definition Document
- [ ] Application Technical Specification
- [ ] API Specification
- [ ] Data Model and ER Diagram
- [ ] Security Architecture
- [ ] Architecture Roadmap
- [ ] Implementation and Migration Plan
- [ ] Risk Register
- [ ] Test Strategy
- [ ] Test Execution Evidence
- [ ] UAT Sign-off
- [ ] Deployment Guide
- [ ] Runbook
- [ ] Release Notes

## Deliverable ownership model

Use the following ownership rule:

- `project-spec.yaml` owns composition and active context.
- `scaffold/architecture-manifest.yaml` owns reusable architecture and technical strategy.
- `products/<slug>/product-spec.yaml` owns product intent, business rules, domain, reports, and workflows.
- formal delivery artifacts elaborate those manifests and provide evidence, traceability, and governance.

That means:

- do not store business rules only in the technical specification,
- do not store stack decisions only in the product spec,
- do not treat implementation code as the only evidence of architecture.

## Suggested artifact storage model

This repository does not yet enforce an artifact directory structure, but the following model is recommended for future use:

```text
deliverables/
`-- <slug>/
    |-- 00-governance/
    |-- 01-vision-requirements/
    |-- 02-business-architecture/
    |-- 03-data-architecture/
    |-- 04-application-architecture/
    |-- 05-technology-architecture/
    |-- 06-technical-specification/
    |-- 07-planning/
    |-- 08-engineering/
    |-- 09-testing/
    `-- 10-release-operations/
```

This is only a recommendation for future organization.

## Phase gates summary

Use these gates to decide whether the project can move forward.

### Gate 0: Ready to define

- Principles exist.
- Governance exists.
- Repository structure exists.
- The project slug is defined and mapped.
- Active manifests are identified.

### Gate 1: Ready for architecture definition

- Scope is approved.
- Stakeholders are known.
- Vision is approved.
- Initial requirements are available.

### Gate 2: Ready for technical specification

- Business, data, application, and technology definitions are coherent.
- Major architecture risks are visible.
- The manifests reflect the agreed target state.

### Gate 3: Ready for implementation planning

- Technical specification is stable enough.
- Requirements are traceable.
- Acceptance criteria are visible.

### Gate 4: Ready to build

- Work packages are sequenced.
- Migration plan exists.
- Governance checkpoints are defined.
- Teams know what to deliver.

### Gate 5: Ready to release

- Quality evidence is sufficient.
- Defects are dispositioned.
- UAT is complete.
- Operations is ready.

### Gate 6: Ready to evolve

- Release is deployed or handed over.
- Operational baseline is documented.
- Changes are logged and impact-assessed.

## How this roadmap applies to the current repository

For the current state of this repo:

- the architecture capability is being defined,
- a concrete product instantiated from `products/<slug>/product-spec.yaml` acts as the validation case,
- the roadmap should be used first to harden the scaffolding itself,
- and later to guide the delivery lifecycle of each product built on top of the scaffolding.

In other words:

- first define the framework,
- then use the framework,
- then generate or implement consistently from it.

## In short

This roadmap gives ArchSpec a formal lifecycle and a complete deliverables inventory.

Use it as:

- a checklist,
- a governance baseline,
- a phase gate model,
- and a definition of what "fully documented and formally engineered" should mean inside this repository.
