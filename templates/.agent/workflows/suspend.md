---
description: Suspend work on the current task
---

1. Run the project's normal validation if practical.
   ```sh
   <validation command>
   ```
2. Update `LOCAL_DEV_NOTES.md` with any reusable command, port, or gotcha discovered this session.
3. Update `.agent/PROJECT_LOG.md` with meaningful decisions or project changes.
4. Update `.agent/REVIEW_QUEUE.md` with known risks or reviewer questions.
5. Update `.agent/session.json` with latest task, status, branch, commit, timestamp, and handoff path if any.
6. Create a handoff under `.agent/handoffs/` if another participant or future session needs more context.
7. Stop local servers that are no longer needed.
8. Tell the human owner the latest state and next recommended action.
