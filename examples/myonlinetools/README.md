# MyOnlineTools case study

MyOnlineTools is the first source project used to validate this system.

## Practices worth generalizing

- Vue 3 + JavaScript + Vite as one frontend implementation option.
- Page-level composition with domain composables for cohesive workflows.
- Shared UI components with documented public contracts.
- Unit/component tests plus Playwright coverage for critical user journeys.
- Dependency auditing, production builds, bundle budgets, and token checks.
- Scheduled/manual Lighthouse audits separated from per-commit correctness gates.
- Explicit handling of API authorization, conflicts, rate limits, and recovery.
- Deployment verification based on actual workflow results.

## Practices that should remain project-specific

- Website navigation domain model and UI.
- GitHub Contents API data persistence implementation.
- Session-based administrator authentication behavior.
- GitHub Pages repository base path.
- Exact bundle budgets and E2E journeys.

The case study deliberately records transferable decisions without copying application source or private configuration.
