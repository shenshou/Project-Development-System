# Performance practice

- Establish a baseline before optimization.
- Track production bundle size where relevant; use budgets as guardrails, not arbitrary goals.
- Prefer route-level or feature-level lazy loading when it materially reduces initial cost.
- Avoid unnecessary dependencies and duplicated runtime code.
- Separate correctness gates from noisy performance measurements.
- Run Lighthouse or equivalent audits on a schedule and before important releases when per-commit cost or variance is not justified.
- Treat lab metrics as comparative evidence, not a guarantee of real-user experience.
