# Testing strategy

Choose tests by risk, not by a target test count.

- **Unit tests:** pure functions, validation, transformations, state transitions, and edge cases.
- **Component tests:** meaningful props, emitted events, slots, loading/disabled states, and interaction behavior.
- **E2E tests:** critical user journeys, authorization boundaries, persistence, import/export, routing, and responsive behavior.
- **Security checks:** dependency audit and targeted checks for secrets, unsafe input handling, or permission mistakes.
- **Build checks:** production build and size budgets when bundle size matters.

Avoid:
- asserting implementation details instead of observable behavior;
- duplicating the same assertion at several layers without added value;
- flaky tests based on arbitrary sleeps;
- adding E2E coverage for every trivial visual detail.

Every test should have a clear failure signal and protect a meaningful behavior.
