---
name: list
description: Display all stored trigger phrases from total-recall.json
allowed-tools: Read
---

# List — Show Trigger Phrases

## Process

1. Read `total-recall.json`. If it doesn't exist, report "No triggers stored yet. Run `/triggered:scan` to generate some."

2. If the user provided a **filter pattern** (e.g., `src/auth`), only show entries whose file path contains that pattern.

3. Display as a formatted table:

```
File                        | Trigger Phrase                 | Confidence | Scanned
--------------------------- | ----------------------------- | ---------- | ----------
src/auth/middleware.ts      | jwt route authentication guard | 0.90       | 2026-03-31
src/db/connection.ts        | database connection pool mgmt  | 0.85       | 2026-03-31
```

4. Show total count at the bottom: `N triggers stored.`
