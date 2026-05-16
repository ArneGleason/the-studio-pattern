# Revelations

This file captures recent discoveries, refinements, and working hypotheses. Promote an item into the canonical docs when it survives use in more than one real project or clearly prevents repeated failure.

## 2026-05-16

### Model Diversity Is A Design Input

The value of a Studio Pattern team is not only that multiple agents can run. It is that the human can choose different models, tools, roles, and environments for the particular kind of judgment needed next. A reviewer, specialist, or second implementer should bring a useful difference in assumptions, capability, or local context.

### Human Hub Beats Opaque Swarm By Default

Direct self-orchestration can be useful when explicitly delegated, but the default pattern keeps the human in the routing center. That lets the human learn the project as it unfolds, notice opportunities between passes, and prevent invisible drift before a large automated run returns with stale assumptions.

## 2026-05-11

### Human Relay Is Experiential Governance

The Warehouse Picking-Basic review loop showed that human-mediated copy and pass-back is not merely overhead. Reading each iteration lets the human owner learn the system over time, adjust direction between agents, and decide which agent behaviors should be reinforced. The pattern should preserve that experience when it improves judgment and orientation.

### PR-Centric Iterations Beat Handoff Rewrites

An implementation handoff works best as the stable orientation layer, similar to a PR description. After review begins, short pass-back notes tied to exact commit SHAs are less brittle than rewriting the whole handoff document for each fix, as long as stale claims are marked superseded.

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

### Canonical Repositories Should Self-Host

Antigravity's first review of this repository found that the canonical pattern repo should dogfood the pattern. This is a useful test: if the pattern cannot make its own evolution easier to review and resume, it is probably too abstract.

### Commit Memory By Default, Exclude Sensitive State Deliberately

The default should be to commit project memory surfaces so they travel across agents and environments. Exceptions should be explicit: secrets, raw logs, local databases, private exports, and volatile runtime state should be ignored or separated.
