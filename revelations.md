# Revelations

This file captures recent discoveries, refinements, and working hypotheses. Promote an item into the canonical docs when it survives use in more than one real project or clearly prevents repeated failure.

## 2026-05-09

### Practical Memory Beats Process Bulk

The useful surfaces in the verified projects are small and close to the work: agent instructions, local developer notes, a project log, a review queue, session state, and handoff notes. The pattern should keep favoring files that agents and humans naturally read during real work.

### Resume And Suspend Need Different Shapes

`warehouse` used suspend/resume to preserve runtime state, including a SQLite database backup. `stem-resolver` used suspend/resume to preserve review context, repo state, and corpus summary. The canonical pattern should define the intent, then let each project decide what must actually be snapshotted.

### The First Reads Matter More Than The File Count

`stem-resolver/AGENTS.md` is effective because it gives a short reading order before listing rules. A future agent should not have to infer where context lives.

### Review Queues Turn Anxiety Into Work

The `stem-resolver` review queue converts vague concern into specific reviewer focus areas. This seems worth keeping as a default template because it makes review cheaper and more targeted.

### Local Adaptation Is A Feature

The central repo should not try to own every project-specific command or runtime detail. Individual repositories should keep their adapted local `.agent/` files and note which canonical pattern version/date/commit they started from.

## Working Hypotheses

- A project should record the Studio Pattern source version/date/commit in `AGENTS.md` and `.agent/session.json`.
- A handoff should fit on one screen when possible, with links to deeper context rather than copying everything.
- Reviewers should be asked to critique project memory itself, not only code.
- Reusable pattern improvements should require at least one concrete field observation.
