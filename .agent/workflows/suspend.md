---
description: Suspend work on the canonical Studio Pattern repository
---

1. Update `.agent/PROJECT_LOG.md` for meaningful pattern decisions.
2. Update `.agent/REVIEW_QUEUE.md` for reviewer questions or known risks.
3. Update `.agent/session.json` with the last task and latest handoff path.
4. Create a concise handoff under `.agent/handoffs/` when another agent or future session needs context.
5. Check git state.
   ```sh
   git status --short
   ```
6. Commit and push if the state should be available to other environments.
