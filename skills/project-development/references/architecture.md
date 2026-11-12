# Architecture guidance

- Define module boundaries around domain capabilities and reasons to change.
- Keep dependencies directed inward where practical; isolate external APIs behind small adapters.
- Prefer page-local state and composables/hooks for cohesive workflows.
- Use a global store only for genuinely cross-cutting state.
- Keep data flow explicit; component inputs flow down and user intent flows up.
- Extract containers, presenters, and domain services only when the boundary clarifies ownership.
- Refactor incrementally and preserve observable behavior.
