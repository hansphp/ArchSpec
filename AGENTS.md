AGENTS OPERATING GUIDELINES

Purpose
- This repository defines the `VibeArchitector` scaffolding itself.
- `VibeArchitector` is a spec-as-source paradigm where implementation and formal engineering deliverables must emerge from structured definitions instead of ad hoc code growth.
- The repository separates three layers:
  - `project-spec.yaml` as the workspace composition manifest.
  - `scaffold/architecture-manifest.yaml` as the reusable technical foundation.
  - `products/<slug>/product-spec.yaml` as the business and UX definition of a concrete product.
- `REFERENCES.md` is the curated methodological knowledge base synthesized from `references/` for stable engineering concepts, lifecycle guidance, and reusable heuristics.
- Source code and formal product deliverables are derived artifacts that emerge from the active composition plus the referenced manifests.

Authority Order
1. Explicit user instructions in the current chat.
2. `project-spec.yaml` for workspace composition and active manifest selection.
3. The manifests referenced by `project-spec.yaml`:
   - `scaffold/architecture-manifest.yaml` for stack and technical rules.
   - `products/<slug>/product-spec.yaml` for domain, behavior, UI, reports, and business rules.
4. `REFERENCES.md` for methodological context, engineering heuristics, and stable conceptual background. It must not override the active manifests.
5. Existing source code, only as the current implementation state.

Core Rule
- Future chats must preserve the separation between reusable scaffolding and product-specific definition.
- The repository must remain reconstructable from `project-spec.yaml` plus its referenced manifests.
- If code and manifests disagree, the manifests are correct unless the user explicitly asks to update them.

Slug Bootstrap Rule
- `<slug>` is a required placeholder, not a product name.
- For a new project, the first concrete action is to resolve `<slug>` from the user's first project-creation prompt.
- Canonical first prompt example:
  - `Create the project "helpdesk-lite" as a new project.`
- Before any product definition or code generation, the resolved slug must be mapped to:
  - `project-spec.yaml` `workspace.source_of_truth.active_product_spec`,
  - `project-spec.yaml` `modules.active_product.id`,
  - `project-spec.yaml` `modules.active_product.path`,
  - `products/<slug>/product-spec.yaml`,
  - and any framework references that describe the active product context.

Expected LLM Interactions
- The agent must be able to execute requests such as:
  - `Create the project "helpdesk-lite" as a new project.`
  - "Create a new application using the same scaffolding."
  - "Change the database engine for every product using this architecture."
  - "Add an entity or a workflow only to the active product."
  - "Generate the full project from the architecture manifest and the product spec."
  - "Derive an E-R diagram, wireframes, or a use-case diagram from the active product."
  - "Draft the technical solution specification or compatibility matrix from the active manifests."
  - "Explain which object or class documentation should exist after implementation."
- These requests must be solved from the correct manifest layer, not by reverse engineering the codebase.

Manifest Requirements
- `project-spec.yaml` must stay focused on composition:
  - active product,
  - active architecture manifest,
  - generation scope,
  - repo-level evolution rules.
- `scaffold/architecture-manifest.yaml` must stay domain-agnostic and describe:
  - runtime and deployment shape,
  - language and framework choices,
  - data and migration strategy,
  - reusable capability modules,
  - stack variation points.
- `products/<slug>/product-spec.yaml` must stay product-specific and describe:
  - domain entities and relationships,
  - business rules and KPI formulas,
  - use cases, workflows, screens, forms, filters, and user actions,
  - reports, imports, and exports.
- If a required behavior is missing, extend the correct manifest first, then apply code changes.

Working Mode
- Always inspect `project-spec.yaml` first.
- Then inspect the referenced architecture manifest and active product spec.
- Inspect `REFERENCES.md` when lifecycle design, methodology, governance, quality, security, delivery artifacts, or cross-project scaffolding decisions are relevant.
- Use the codebase only to:
  - measure drift between implementation and manifests,
  - apply requested implementation changes,
  - verify that generated artifacts match the manifests.

Reference Use
- Treat `REFERENCES.md` as the preferred entry point to the research archive in `references/`.
- Use raw files inside `references/` only when deeper context is needed.
- Never treat `REFERENCES.md` or `references/` as the business source of truth for the active product.

Tracking Boundary
- The framework repository does not keep an internal backlog or iteration log for framework evolution.
- Assume framework planning and backlog management happen outside the repository, for example in GitHub Issues or GitHub Projects, unless the user explicitly asks otherwise.
- If a concrete product later defines its own backlog or delivery tracking, that tracking belongs in the product repository under `source/`, not at the framework root.

Source Workspace
- The `source/` path is the reserved product workspace root.
- In the framework repository, `source/` should stay absent or empty until a product repository is cloned or initialized there.
- A new product repository may own its own `.git` directory under `source/`.
- Generated and developed product files must live inside that product repository under `source/`.
- For web products, `source/src/` is the default internal application root unless the active manifests state otherwise.
- Runtime files such as `source/Dockerfile` belong inside `source/`, not at the framework root.
- The framework repository must not keep placeholder application files inside `source/`.

Drift Policy
- If the architecture manifest is newer or clearer than the code, update the code to match it.
- If the product spec is newer or clearer than the code, update the code to match it.
- If a product requirement cannot be expressed with the current architecture manifest, extend the architecture manifest before changing code.
- Never invent business rules or stack rules from code alone when the manifests are silent.

Rebuild Policy
- The repository must support a full rebuild from `project-spec.yaml` and its referenced manifests.
- A future chat must be able to recreate the project without relying on prior source files.
- Generated outputs may vary in formatting, but must preserve the declared behavior and constraints.

Change Protocol
- For composition changes, edit `project-spec.yaml` first.
- For stack or runtime changes, edit `scaffold/architecture-manifest.yaml` first.
- For business or UX changes, edit `products/<slug>/product-spec.yaml` first.
- Then propagate the change to:
  - models and schemas,
  - database migrations,
  - API and services,
  - UI and forms,
  - reports and templates,
  - traceability matrices and API specifications,
  - data dictionaries and architecture diagrams,
  - diagrams and wireframes,
  - technical specifications, security-access matrices, and compatibility matrices,
  - object-model documentation and test suites,
  - deployment guides, runbooks, and release notes when relevant,
  - docker and runtime files inside `source/`.
- Record durable structural decisions in `adrs/` when the framework contract changes materially.

Project Defaults
- Current active architecture manifest:
  - Python backend with FastAPI.
  - SQLAlchemy ORM.
  - Alembic migrations.
  - SQLite default engine.
  - React + Vite frontend.
  - ECharts for dashboards.
  - WeasyPrint and openpyxl for reports.
- Current active product placeholder:
  - `<slug>` via `products/<slug>/product-spec.yaml` until the first project-creation prompt resolves it.

Execution Rules
- Prefer `rg` and `rg --files` for search.
- Keep edits ASCII unless there is a strong reason not to.
- Use `apply_patch` for manual file edits.
- Never revert user changes unless explicitly requested.
- If unexpected conflicting changes appear, stop and ask.

Communication Rules
- Be concise and direct.
- Explain assumptions, prerequisites, and next actions clearly.
- When reporting project work, reference the relevant manifest as the origin of truth when applicable.
