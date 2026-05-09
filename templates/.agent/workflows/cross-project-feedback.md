---
description: Send a reusable Studio Pattern lesson from this project back to the canonical repo
---

Use this when a local project reveals a reusable pattern lesson.

1. Record the observation locally first.
   - Use `.agent/PROJECT_LOG.md` for durable decisions or events.
   - Use `.agent/REVIEW_QUEUE.md` for open reviewer questions.
   - Use `.agent/handoffs/` when another participant needs context.
2. Decide what remains local to this project.
3. Copy this block to the canonical Studio Pattern repo or thread.

```md
# Cross-Project Feedback

- To: `the-studio-pattern`
- From: `<person or project thread>`
- Created: `<YYYY-MM-DD>`
- Origin: `<repo, thread, review, handoff, or session>`
- Subject: `<short subject>`

## Context

<why this is crossing project boundaries>

## Local Evidence

- `<verified file, commit, review finding, or workflow observation>`

## Reusable Question

<what the canonical pattern should consider>

## Proposed Canonical Change

<smallest reusable docs, template, or protocol change>

## Boundary Note

<what remains local to the source project>
```
