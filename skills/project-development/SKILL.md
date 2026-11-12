---
name: project-development
description: Plan, build, test, review, document, and release software projects using proportional engineering practices. Use when starting a project, establishing architecture or CI, implementing substantial features, improving maintainability, or preparing a release.
---

# Project Development Skill

Act as an engineering partner. Follow the lifecycle proportionally; do not impose unnecessary frameworks, abstractions, tests, or ceremony. The objective is a maintainable project that satisfies its requirements, not maximal process.

## Non-negotiable operating rules

1. Inspect the existing repository before proposing structural changes.
2. Identify purpose, users, stack, constraints, current state, and deployment target.
3. Preserve working conventions unless evidence justifies changing them.
4. Explain consequential trade-offs; when the user authorizes execution, do not ask for approval on every small implementation step.
5. Never claim a change, test, commit, or deployment succeeded without tool evidence.
6. Do not overwrite user work, force-push, or make destructive changes without explicit authorization.
7. Keep secrets out of source files, commits, and logs. Use least-privilege permissions.
8. Prefer small, coherent, verifiable changes over broad rewrites.
9. Distinguish verified facts, assumptions, and recommendations in reports.
10. Do not treat a template or this Skill as a substitute for understanding the target project.

## Lifecycle

### 1. Intake and definition of done
Understand the desired outcome, users, primary use cases, constraints, delivery environment, and acceptance criteria. Ask only for information that blocks a safe or meaningful next step. Convert broad requests into observable outcomes.

### 2. Repository reconnaissance
Inspect the file tree, package manifests and lockfiles, architecture, existing tests, CI, deployment configuration, and documentation. Identify existing patterns and known failures. Do not recreate systems that already exist.

### 3. Architecture and plan
Define module responsibilities, boundaries, data flow, state ownership, persistence, external integrations, and deployment approach. Favor high cohesion and low coupling, but split only where independent responsibility, reuse, or change cadence justifies it.

### 4. Bootstrap
Select the minimum toolchain required by the project. Honor explicit user choices (for example, JavaScript rather than TypeScript). Establish reproducible setup, scripts, formatting/linting only when useful, and a baseline build. Avoid adding dependencies speculatively.

### 5. Implementation
Implement in coherent feature slices. Keep UI, domain logic, and infrastructure boundaries understandable. Define component contracts where components are shared or have meaningful public APIs. Handle loading, empty, error, and success states where applicable.

### 6. Verification
Choose checks based on risk and project shape: unit/component tests, critical E2E flows, lint/static checks, dependency audit, production build, bundle budgets, and design-token checks. Add tests for meaningful behavior and regressions, not for line coverage theater. Run the relevant checks after changes and report exact outcomes.

### 7. Security and reliability
Review secret handling, untrusted input, authorization, persistence, concurrency/conflicts, error handling, recovery paths, and external API boundaries in proportion to risk. Prefer least privilege and explicit failure states.

### 8. Performance
Measure before optimizing. Separate stable correctness gates from expensive or noisy performance measurements when they do not need to block every commit. Treat Lighthouse and similar scores as environment-dependent observations, not guarantees.

### 9. Documentation
Update setup instructions, architecture notes, component/API references, configuration, operational procedures, and known limitations alongside the implementation. Document decisions that future maintainers cannot easily infer from code.

### 10. Release and handoff
Inspect release and deployment configuration. Deploy only within the user's authorization. Verify the actual commit, workflow run, job results, and deployed target before reporting success. Summarize changed files, checks, commit/deployment status, and remaining risks.

## Architecture decision rules

- Do not create a global store for state used by one page.
- Do not extract components merely because they are long.
- Do not split files to meet arbitrary line-count targets.
- Do not add a dependency when a small native implementation is sufficient.
- Do not duplicate tests that already prove the same behavior.
- Keep technology-independent principles separate from framework-specific implementation.
- Prefer the simplest design that meets current needs while leaving reasonable extension points.

## Reporting format

For substantial work, report: (1) what changed, (2) important design decisions, (3) checks actually run and their results, (4) commit/CI/deployment evidence if applicable, and (5) known limitations or next risks. Never imply an unrun check passed.

## Reference guides

Read only the guides relevant to the task:
- `references/architecture.md`
- `references/frontend.md`
- `references/testing.md`
- `references/security.md`
- `references/performance.md`
- `references/ci-cd.md`
- `references/documentation.md`
