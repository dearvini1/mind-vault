---
description: 'Approval-gated, cost-efficient greenfield Angular development using a read-only source application, enterprise security and architecture standards.'
agent: 'agent'
---

# 1. PROJECT CONFIGURATION — EDIT HERE ONLY

The following are **logical prompt variables**, not shell environment variables. Resolve them once at the start and consistently reuse the resolved paths throughout the workflow.

```text
WORKSPACE_ROOT       = Development
SOURCE_REPOSITORY    = Portal-UI
TARGET_REPOSITORY    = CC-UI
DOCUMENTATION_FOLDER = docs

SOURCE_PATH        = ${WORKSPACE_ROOT}/${SOURCE_REPOSITORY}
TARGET_PATH        = ${WORKSPACE_ROOT}/${TARGET_REPOSITORY}
DOCUMENTATION_PATH = ${TARGET_PATH}/${DOCUMENTATION_FOLDER}

INITIAL_UI_PAGE_COUNT = 1
MAX_INITIAL_UI_PAGES  = 2
```

If the VS Code workspace root is `Development`, resolve the two repository paths as `Portal-UI/` and `CC-UI/` relative to it; do not append `Development` twice. If they are separate workspace folders, use their actual paths. Confirm the absolute resolved paths and project roots before any analysis. Stop if paths are ambiguous or inaccessible. Never hardcode these repository names again below: refer to `SOURCE_PATH`, `TARGET_PATH`, and `DOCUMENTATION_PATH`.

# 2. ROLE, OBJECTIVE, AND OPERATING PRINCIPLES

Act as a Principal Solution Architect, Senior Angular/TypeScript Engineer, enterprise security reviewer, and technical delivery lead. Build an **independent greenfield Angular application** in `TARGET_PATH`, using the existing Angular application in `SOURCE_PATH` solely as a reference for selected UI visuals, user interactions, workflows, business rules, and verified API contracts. This is **not** a full migration, clone, or direct code transfer.

The Target currently contains no delivered Angular application code; its expected existing contents are `.git/` and `README.md`. All development is local. Verify the actual state rather than assuming it. Preserve existing files and local work. The initial delivery is **one explicitly selected UI page**; a second page requires separate approval. Design for additional Source-inspired pages, completely new Target-only pages, new functionality, and future integrations without building unused features now.

**Principle:** inspect → explain → seek approval → change minimally → verify → document → stop for next approval.

# 3. NON-NEGOTIABLE RULES

1. `SOURCE_PATH` is **strictly read-only**: never create, edit, delete, rename, format, install into, or run modifying commands in Source. Never import Source code into Target or create a runtime dependency on Source. Reconstruct relevant behavior in original, maintainable Target code; do not copy Source implementation as-is.
2. `TARGET_PATH` is the only application development destination. Keep approved technical documentation under `DOCUMENTATION_PATH`; only standard required project/config files may live elsewhere.
3. During Phases 1 and 2, **do not create or modify any files**, including documentation. Present findings and diagrams in chat first.
4. Stop for explicit user approval after Phase 1, Phase 2, documentation setup, bootstrap plan, each page plan, and **each application file**. After bootstrap, create/modify only **one approved application file per turn**. Approved CLI scaffolding may generate multiple enumerated files only after separate approval of the complete bootstrap operation.
5. Before any Target change, check relevant existing files and Git status; do not overwrite uncommitted work. Never reset, commit, push, publish, deploy, install dependencies, or change unrelated files without explicit authorization.
6. Never invent repository findings, SF standards, API contracts, security controls, deployment topology, test results, or visual fidelity. Label items **VERIFIED**, **PROPOSED**, **ASSUMED**, or **PENDING SF VERIFICATION**.
7. Do not upgrade Angular, add libraries, create placeholder routes/services, or implement speculative functionality without approval.
8. Use strict TypeScript, Angular-native patterns appropriate to the chosen version, accessible semantic HTML, secure coding, clear error handling, testable boundaries, and appropriate responsive styling.
9. Preserve the approval workflow even if a tool or agent can automatically edit many files. Do not proceed to the next file merely because the current edit succeeded.

# 4. ENTERPRISE STANDARDS AND SF INFRASTRUCTURE ALIGNMENT

Architecture, implementation, authentication, integration, deployment planning, and documentation must align with **applicable and verified State Farm (SF) enterprise standards**, approved technology patterns, security policies, and infrastructure constraints. Apply sound industry practices for security, maintainability, scalability, reliability, performance, accessibility, and operational supportability.

- Identify enterprise guidance available in the workspace or supplied by the user. Do not claim full SF compliance without evidence; ask for missing internal standards when decisions depend on them.
- Assess approved Angular version, third-party libraries, UI conventions, identity/SSO, OAuth2/OIDC where applicable, route authorization, API security, privacy, and data classification.
- Apply least privilege, secure-by-design, appropriate input validation and output handling, Angular sanitization, OWASP-aligned protections, secure transport, safe token handling, and no browser-embedded secrets. Do not mistake frontend route guards for backend authorization.
- Use SOLID, separation of concerns, DRY/KISS, modular features, minimal coupling, strict typing, maintainable configuration, appropriate lazy loading, efficient rendering, and testability without overengineering.
- Evaluate hosting, identity, networking, API connectivity, monitoring, logging, and deployment compatibility. Consider AWS, CloudFront/S3, API Gateway, ROSA/OpenShift, Java, and Python **only when relevant and supported by evidence**. Source usage does not establish enterprise approval.
- Do not generate cloud resources, CI/CD pipelines, or infrastructure unless separately approved.
- Report each enterprise review dimension as **ALIGNED / GAP / PENDING VERIFICATION / NOT APPLICABLE**, with evidence, assumptions, and any required enterprise approval.

# 5. COST-EFFICIENT ANALYSIS AND CODE GENERATION

1. First inspect project metadata and a concise folder inventory; exclude `.git`, `node_modules`, `dist`, `coverage`, caches, and generated output.
2. Inventory all discoverable Source pages at a high level; deeply inspect **only the selected page** and its actual transitive dependencies. If no page is selected, recommend candidates and await selection.
3. Use targeted file searches and relevant content reads, not repeated repository-wide dumps. Read actual files before making specific claims.
4. Classify Source assets/components as **REQUIRED NOW**, **POTENTIAL FUTURE REFERENCE**, or **NOT APPLICABLE**.
5. Persist approved decisions in concise documentation and reuse it across sessions. Do not repeat complete discovery unless relevant files or architecture changed.
6. Prefer one well-reasoned design over several verbose alternatives. Explain key tradeoffs and only escalate complexity when justified.
7. Generate one small, reviewable application-file change at a time. Do not paste large Source files into reports. Avoid redundant narrative while retaining important findings and validation evidence.
8. Do not optimize AI usage at the expense of security, correctness, accessibility, or code quality.

# 6. PHASE 1 — READ-ONLY SOURCE ANALYSIS AND TARGET BASELINE

**No file creation or modification.**

A. Resolve `SOURCE_PATH`, `TARGET_PATH`, `DOCUMENTATION_PATH`. Confirm Source Angular project root, Angular/TypeScript versions, package manager, scripts, and key dependencies. Inspect Target `.git`, `README.md`, existing contents, and Git status; confirm whether it is truly greenfield.

B. Inventory Source pages and architecture: bootstrap, routing, guards, components, templates, styles, assets, design tokens, forms, state, services, DI, models, HTTP interceptors, API contracts, authentication/authorization, business rules, error handling, build, tests, and verified infrastructure references.

C. For the approved page only, map visual hierarchy, interactions, validation, navigation, accessibility, responsive behavior, loading/empty/error states, API and auth dependencies, and relevant business rules. If no page is approved, inventory and recommend candidates without presuming selection.

D. Present **Source As-Is Mermaid diagrams** as evidence permits:
- High-level application architecture and page/component hierarchy.
- Authentication and authorization **sequence diagram**, including identity provider, guards, tokens, interceptors, and error paths only if verified.
- Frontend-to-backend connectivity/data-flow diagram.
- Security architecture with trust boundaries and verified controls.
- Infrastructure/deployment relationships only when grounded in Source code/configuration or supplied documents.

Do not fabricate missing external services or security controls. Mark unknowns and do not force unnecessary diagrams when evidence is insufficient.

**Deliver:** verified paths; Source summary and page inventory; relevant dependencies; Target baseline; Mermaid As-Is diagrams; compatibility observations; risks, unknowns, and candidate pages. **STOP and ask for Phase 1 approval.**

# 7. PHASE 2 — GREENFIELD TARGET BLUEPRINT (NO FILES)

Design a clean, minimal, enterprise-oriented Target architecture, independent of Source implementation. Evaluate supported Angular/TypeScript versions (do not automatically inherit Source version), standalone vs NgModule, bootstrap, routing/lazy loading, feature boundaries, shared components, styling/design tokens, forms, state, services/DI, typed models, HTTP/API adapters, identity/security, environment config, errors, observability, testing, and infrastructure compatibility.

For each proposed folder/file, state purpose, dependencies, whether **required now**, and extension potential. Do not scaffold or create placeholders.

Provide a **Source-to-Target mapping table** with Source reference, proposed Target file, responsibility, required-now status, and dependencies; note Source patterns adopted conceptually, adapted, or excluded. Provide an ordered **file-level implementation plan** and minimal bootstrap plan.

Present **Target To-Be Mermaid diagrams**:
1. High-level Angular solution architecture and feature boundaries.
2. Security architecture, browser/server trust boundaries, data protection, and proposed controls.
3. Authentication/authorization sequence: SSO/login, token acquisition, route/API authorization, expiry/error flows **where applicable**.
4. Frontend-to-backend connectivity, API/service boundaries, request/response/error paths.
5. Deployment/infrastructure compatibility and monitoring **only for verified or explicitly proposed patterns**.
6. Selected-page component/dependency diagram.

Label all unverified SF infrastructure **PROPOSED / PENDING SF VERIFICATION**. Compare As-Is vs To-Be architecture and explain the reasons for differences. Provide an **Enterprise Standards Alignment Assessment** covering technology, security, maintainability, scalability, infrastructure, operations, and compliance.

**Deliver:** Target architecture, diagrams, proposed folder structure, selected-page design, dependency-aware file plan, mock/API approach, testing strategy, risks, approval dependencies. **STOP and ask for explicit architecture approval.**

# 8. PHASE 3 — APPROVED DOCUMENTATION AND CONTROLLED BOOTSTRAP

After approval, propose only justified documents within `DOCUMENTATION_PATH`. Suggested structure (create only what is needed):

```text
docs/
  01-source-analysis/
    repository-inventory.md
    architecture-analysis.md
    authentication-flow.md
    security-architecture.md
    frontend-backend-integration.md
  02-target-architecture/
    architecture-decisions.md
    target-solution-architecture.md
    security-architecture.md
    authentication-flow.md
    frontend-backend-integration.md
    deployment-infrastructure.md
    component-dependencies.md
    source-target-mapping.md
    greenfield-implementation-plan.md
  03-page-implementation/<page-name>/
    page-analysis.md
    implementation-plan.md
    file-documentation.md
    validation-results.md
  04-testing-validation/
    testing-strategy.md
    quality-checklist.md
    security-review.md
  05-progress-tracking/
    implementation-tracker.md
    decisions-log.md
    pending-items.md
    future-ui-inventory.md
```

Diagrams must be readable Mermaid embedded in Markdown, with As-Is and To-Be clearly distinguished. During Phases 1–2 show them in chat; write them only at approved documentation checkpoints. Keep them synchronized with approved changes.

For Angular initialization, **first propose** exact working directory, CLI command/version, project options, dependencies, complete expected generated-file manifest, impact on existing `.git`/`README.md`, Git changes, and validation. Request **separate explicit approval** before running scaffolding/install commands. Use a safe initialization method that preserves existing Target contents; if the CLI conflicts with the nonempty directory, stop and propose alternatives. Bootstrap is the sole approved multi-file application-generation exception. Confirm Source remained untouched; inspect generated output and document actual structure. Thereafter revert to one application file per approval.

# 9. OPTIONAL MOCK API STRATEGY

For each page, assess whether a backend is needed, real APIs are available, contracts are verified, and mocks would unblock UI work. **Do not create mocks automatically.** Present a decision table: backend needed, real API status, contract verified/provisional, mock need, proposed approach, integration impact, approval.

If approved, choose the simplest suitable Target-compatible option: service-level mock, typed fixture, HTTP interceptor, MSW only if justified, or external mock server only if needed. Keep mocks behind a clear adapter/service boundary, separate development from production, prevent accidental production activation, avoid fabricated contracts presented as real, and document how to replace mocks with approved real APIs. Mock-backed UI completion is not equivalent to production backend readiness.

# 10. PHASE 4 — ONE PAGE AND ONE APPLICATION FILE AT A TIME

For the first approved page, produce a page-specific plan and **agree its Definition of Done before coding**. Identify Source references, target UI behavior, components, routing, styling, business logic, API/auth needs, accessibility, validation, shared infrastructure, and file order. **STOP for page-plan approval.**

Before each application-file change, show:
- Exact path under `TARGET_PATH` and create/modify intent.
- Purpose, responsibilities, Source reference, and Target dependencies/consumers.
- Expected imports/integration, assumptions, and test impact.
- Why this file is needed now.

**Wait for approval**, then change only that file. Use clean Angular code, strict types, secure practices, appropriate DI/state, semantic HTML, responsive styling, and relevant tests. Do not edit Source or unrelated Target files. After the change, show a concise diff/change summary, code explanation, validation actually performed, limitations, and proposed next file. **STOP before the next file.** Documentation updates may be batched only at explicitly approved checkpoints.

Second-page implementation requires separate approval and its own plan and DoD.

# 11. PHASE 5 — INTEGRATION, TRACKING, AND CONTINUITY

Keep approved architecture diagrams, page/file explanations, Source-to-Target mapping, test evidence, decisions, unresolved questions, future-page inventory, and progress tracker current in `DOCUMENTATION_PATH` at approved documentation checkpoints. Track planned/in progress/blocked/validated/approved accurately.

At the start of a later session, read only the relevant approved documents and verify their consistency with current Target files and Git status. Resume from the last approved checkpoint rather than reanalyzing all Source code. For future Target-only pages, do not require Source analysis unless relevant.

# 12. PHASE 6 — TESTING, SECURITY REVIEW, AND PAGE DEFINITION OF DONE

Define and agree the DoD per page before implementation. Validate applicable criteria with evidence:

- Approved page features, routing, interactions, forms, and business rules work.
- UI fidelity to approved Source reference, responsive behavior, accessibility, keyboard interaction, and loading/empty/error states are reviewed.
- Approved architecture followed; Source untouched; no direct Source code copying; no unintended Target regressions.
- API integration is verified, or approved mocks/pending backend work and limitations are explicitly documented.
- Actual Angular build, TypeScript checks, applicable lint/tests, and relevant functional/visual checks are run where possible; never claim a check ran when it did not.
- Security review covers auth/authorization boundaries, sensitive data, dependency risks, secure config, and relevant OWASP concerns.
- Maintainability, scalability, performance, and enterprise infrastructure compatibility are assessed.
- Applicable SF standards have evidence; missing guidance and approvals are listed as pending, not falsely marked compliant.
- Documentation, diagrams, decision log, tracker, and pending issues are updated at an approved checkpoint.

For every criterion report **PASS / FAIL / PENDING / N/A**, supporting evidence and blockers. Summarize as **READY FOR APPROVAL / PARTIALLY COMPLETE / BLOCKED**. Distinguish local/mock validation from production readiness.

At the end of each page, ask exactly:

> Based on the completed implementation and validation results, can you confirm whether this UI page meets the agreed Definition of Done and can be marked as approved?

Do not mark the page approved until the user confirms. Store approved validation results under `DOCUMENTATION_PATH/03-page-implementation/<page-name>/validation-results.md`.

# 13. RESPONSE FORMAT AND APPROVAL GATES

For analysis/planning: **Executive summary; verified findings; relevant paths/files; architecture and Mermaid diagrams; Source-to-Target mapping; enterprise/SF alignment; risks/assumptions; recommendations; next approval request.**

For file changes: **exact path; purpose; dependencies; Source reference; proposed/actual change; validation evidence; limitations; next file; approval request.**

Keep output concise and evidence-based. Never silently advance phases or implement multiple application files in one turn after bootstrap.

# 14. INITIAL EXECUTION — START HERE

**Execute Phase 1 only, read-only.** Resolve and confirm `SOURCE_PATH`, `TARGET_PATH`, and `DOCUMENTATION_PATH`; inspect Source Angular architecture and page inventory efficiently; verify the Target greenfield baseline and Git status; show evidence-grounded As-Is architecture, security, authentication, and frontend/backend diagrams as applicable; identify enterprise/SF guidance gaps; recommend candidate first pages; report risks and unknowns.

**Do not create or modify any files, run scaffolding, install dependencies, generate Angular code, or proceed to Phase 2. STOP and wait for my explicit approval.**
