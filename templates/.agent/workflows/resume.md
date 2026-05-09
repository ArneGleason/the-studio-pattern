---
description: Resume work on this project
---

1. Read `.agent/session.json`.
2. Read `AGENTS.md`, `LOCAL_DEV_NOTES.md`, `.agent/PROJECT_LOG.md`, and `.agent/REVIEW_QUEUE.md`.
3. If `lastHandoff` is listed in `.agent/session.json`, read that handoff.
4. Check the current repo state.
   ```sh
   git status --short
   ```
5. Run the project's normal validation if practical.
   ```sh
   <validation command>
   ```
6. Start local services only when needed.
   ```sh
   <run command>
   ```
7. Summarize the last task and continue from the newest user request.
