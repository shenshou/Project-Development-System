# Security and reliability

- Keep credentials out of source control, logs, screenshots, and generated artifacts.
- Use least-privilege tokens and document required scopes.
- Treat imported files, API responses, URLs, and user content as untrusted input.
- Validate data at system boundaries; enforce file size limits before expensive parsing when possible.
- Classify API errors and present actionable messages without leaking secrets.
- Do not automatically retry non-idempotent writes unless the operation has a safe idempotency strategy.
- For conflict-prone writes, preserve user changes and provide explicit recovery paths.
- Document data ownership, persistence, backup, and recovery behavior.
