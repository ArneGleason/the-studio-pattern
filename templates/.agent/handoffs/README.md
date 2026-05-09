# Handoffs

Store timestamped handoff notes here when work crosses sessions, models, reviewers, or environments.

Suggested filename:

```txt
YYYYMMDD-HHMMSS-short-task-name.md
```

Each handoff should summarize what changed, current state, checks run, checks not run, reviewer starting points, and open questions.

Write handoffs for the human owner first. The next reader may be another agent, but the human should be able to understand the state, add context, and decide where the work should go next.

For handoffs that cross project, repository, or thread boundaries, add this traceability header near the top:

```md
- To: `<destination project or thread>`
- From: `<person, agent, source project, or source thread>`
- Created: `<YYYY-MM-DD>`
- Origin: `<source repo, commit, review, handoff, or session>`
- Subject: `<short subject>`
```
