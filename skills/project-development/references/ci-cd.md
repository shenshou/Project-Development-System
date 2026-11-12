# CI/CD guidance

A typical pipeline may include install, lint/static checks, unit tests, E2E tests, security audit, production build, artifact upload, and deployment. Select gates based on project risk and runtime cost. Keep deployment permissions scoped. Pin third-party actions to reviewed versions or immutable SHAs according to organizational policy. Verify workflow results and deployed output before reporting success.
