# Frontend guidance

For Vue projects:
- Use Vue 3 Composition API and JavaScript or TypeScript according to project requirements.
- Keep page components responsible for composition and coordination.
- Use composables for reusable stateful logic; pure utilities for deterministic transformations.
- Define component props, emits, slots, defaults, and examples.
- Keep design tokens centralized when the UI has multiple pages or a meaningful design system.
- Handle loading, empty, error, disabled, and success states deliberately.
- Avoid unnecessary global event buses and hidden mutable shared state.

For other frameworks, translate the principles rather than copying Vue-specific patterns.
