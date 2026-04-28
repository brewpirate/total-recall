---
name: forget
description: Remove trigger phrases for a file or glob pattern from total-recall.json
allowed-tools: Read, Edit
---

# Forget — Remove Trigger Phrases

## Process

1. Read `total-recall.json`. If it doesn't exist or is empty, report "No triggers to forget."

2. Match the user's argument against stored file paths:
   - Exact path match
   - Glob/substring match (e.g., `src/auth/*` removes all auth triggers)

3. Remove matching entries from the triggers object.

4. Write the updated file back.

5. Report what was removed:
   ```
   Removed 3 triggers:
   - src/auth/middleware.ts (jwt route authentication guard)
   - src/auth/session.ts (session token management)
   - src/auth/roles.ts (role based access control)
   ```

6. If nothing matched, report "No triggers matched that pattern."
