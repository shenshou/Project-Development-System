# Security guidance

Use least privilege, keep secrets outside source control, validate all untrusted boundaries, limit uploaded input, classify errors, and design safe write/recovery semantics. Never expose tokens in URLs, browser storage, logs, or documentation unless the architecture explicitly requires a carefully reviewed client-side token flow.
