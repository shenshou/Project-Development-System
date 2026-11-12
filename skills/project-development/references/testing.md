# Testing guidance

Select a balanced test pyramid based on product risk:
- unit tests for pure logic and edge cases;
- component tests for public UI behavior;
- E2E tests for critical end-to-end journeys.

Prefer deterministic tests, explicit fixtures, accessible selectors, and assertions on user-visible outcomes. Do not optimize for raw test count.
