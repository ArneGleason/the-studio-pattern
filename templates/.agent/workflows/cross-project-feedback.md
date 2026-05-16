---
description: Send a reusable Studio Pattern lesson from this project to another project or the canonical repo
---

# Cross-Project Feedback

Use this when a lesson, review result, retrospective, or boundary clarification needs to move from one project to another.

Do not use this for every local decision. Use it when the destination project would otherwise lose track of where the idea came from or why it should change the canonical pattern.

1. Record the observation locally first.
   - Use `.agent/PROJECT_LOG.md` for durable decisions or events.
   - Use `.agent/REVIEW_QUEUE.md` for open reviewer questions.
   - Use `.agent/handoffs/` when another participant needs context.
   - Use `LOCAL_DEV_NOTES.md` for source-project commands, environment quirks, ports, or local setup gotchas.
2. Ask the human owner to read the summary and add any stakeholder context.
3. Decide what remains local to the source project.
4. Copy this block to the destination project or thread. For feedback to the canonical repo, set `To` to `the-studio-pattern`.

```md
# Cross-Project Feedback

- To: `<destination project or thread>`
- From: `<person, agent, source project, or source thread>`
- To agent: `<agent or tool, if relevant>`
- To machine: `<machine-handle, if relevant>`
- From agent: `<agent or tool, if relevant>`
- From machine: `<machine-handle, if relevant>`
- Created: `<YYYY-MM-DD>`
- Origin: `<source repo, commit, review, handoff, or session>`
- Subject: `<short subject>`

## Context

<why this is crossing project boundaries>

## Local Evidence

- `<verified file, commit, review finding, retrospective note, or workflow observation>`

## Reusable Question

<what the destination project or canonical pattern should consider>

## Proposed Canonical Change

<smallest reusable docs, template, or protocol change>

## Boundary Note

<what remains local to the source project>
```

For mid-project retrospectives, add these prompts when useful:

```md
## What Worked

- ...

## What Hurt

- ...

## Pattern Changes Proposed

- ...

## Project-Only Notes

- ...

## Practice To Adopt Immediately

- ...
```
