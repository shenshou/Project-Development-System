# Project lifecycle

Use these stages proportionally. A small static site does not need the same ceremony as a multi-user business application.

1. **Intake** — define users, outcomes, scope, constraints, risks, and acceptance criteria.
2. **Technical selection** — choose runtime, framework, storage, integrations, hosting, and operational constraints.
3. **Architecture** — define modules, boundaries, state ownership, data flow, error handling, and deployment topology.
4. **Bootstrap** — establish repository conventions, scripts, environment handling, linting, and minimal design foundations.
5. **Implementation** — deliver vertical slices; keep business logic separate from presentation where that improves clarity.
6. **Verification** — select unit, component, integration, and E2E tests based on risk and user-visible behavior.
7. **Security and reliability** — validate inputs, protect credentials, classify errors, and design safe recovery paths.
8. **Performance** — measure before optimizing; track bundle size and user-perceived performance where relevant.
9. **Documentation** — document setup, architecture decisions, public component APIs, operations, and release steps.
10. **Release** — run quality gates, deploy, verify the actual deployment, and record known limitations.

## Completion criteria

A project is ready for routine development when a new contributor can install it, run it, test it, build it, understand its major boundaries, and deploy it using documented steps.
