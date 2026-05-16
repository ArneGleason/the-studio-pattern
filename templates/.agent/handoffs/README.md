# Handoffs

Store timestamped handoff notes here when work crosses sessions, models, reviewers, or environments.

Suggested filename:

```txt
YYYYMMDD-HHMMSS-short-task-name.md
```

Each handoff should summarize what changed, current state, checks run, checks not run, reviewer starting points, and open questions.

When asking for review, also include:

```md
- Role requested: <reviewer | lead developer | specialist | future session>
- Allowed actions: <static review | smoke test | implementation | docs update | etc.>
- Disallowed actions: <optional boundaries>

## Review Target

- Repo: <repo>
- Branch: <branch>
- Commit: <commit>
- Base: <base branch or commit>
- PR or compare URL: <url-or-none>
- Requirements source: <file, directory, issue, or handoff>
- Local checkout status: <known-clean | dirty | unavailable | unknown>
```

Write handoffs for the human owner first. The next reader may be another agent, but the human should be able to understand the state, add context, and decide where the work should go next.

For handoffs that cross project, repository, or thread boundaries, add this traceability header near the top:

```md
- To: `<destination project or thread>`
- From: `<person, agent, source project, or source thread>`
- Created: `<YYYY-MM-DD>`
- Origin: `<source repo, commit, review, handoff, or session>`
- Subject: `<short subject>`
```

When work moves between physical machines or local environments, add machine context:

```md
- To agent: `<agent or tool>`
- To machine: `<machine-handle>`
- From agent: `<agent or tool>`
- From machine: `<machine-handle>`
```

Machine handles are human-assigned labels such as `macbook-pro-m5` or `mac-mini-pro-m4`; do not infer them from OS hostname without confirmation.
