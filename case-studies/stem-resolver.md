# Stem Resolver Case Study

This case study is based only on files verified locally under `/Users/arnegleason/code/github.com/arnegleason/stem-resolver`.

## Verified Files

- `AGENTS.md`
- `LOCAL_DEV_NOTES.md`
- `docs/studio-pattern.md`
- `scripts/studio-session.js`
- `.agent/PROJECT_LOG.md`
- `.agent/REVIEW_QUEUE.md`
- `.agent/session.json`
- `.agent/workflows/resume.md`
- `.agent/workflows/suspend.md`
- `.agent/handoffs/20260509-135204-initial-antigravity-review-setup.md`

## What Stem Resolver Shows

Stem Resolver is a newer, clearer adaptation of the Studio Pattern.

The verified `AGENTS.md` gives new agents a fast orientation path:

1. read the project README,
2. read `LOCAL_DEV_NOTES.md`,
3. read `docs/studio-pattern.md`,
4. check `.agent/PROJECT_LOG.md` and `.agent/REVIEW_QUEUE.md`.

It identifies the project as using a pattern where one lead developer advances the project and a separate reviewer reviews from another perspective. It also instructs agents to update local notes and the project log, run validation before handoff, and generate a reviewer handoff.

The verified `LOCAL_DEV_NOTES.md` records:

- the local run command,
- the default URL,
- corpus storage locations,
- validation command,
- Studio Pattern status/handoff/suspend/resume commands,
- GitHub and corpus-publishing notes.

The verified `docs/studio-pattern.md` names the roles: human owner, lead developer, reviewer, and specialist agent. It defines memory surfaces and protocols for handoff, review, and decisions.

The verified `.agent/PROJECT_LOG.md` records project creation decisions and notes that the Warehouse pattern was adapted into Stem Resolver as root agent instructions, local notes, project log, review queue, handoff workflow, and session state.

The verified `.agent/REVIEW_QUEUE.md` gives an initial reviewer focused questions about manifest write safety, schema design, UI cataloging speed, GitHub-as-sync, and whether the memory surfaces are sufficient.

The verified `.agent/session.json` records:

- project name,
- studio mode,
- current lead,
- intended reviewer,
- last task,
- status,
- timestamp,
- last handoff path,
- branch,
- corpus summary.

The verified `.agent/workflows/resume.md` and `.agent/workflows/suspend.md` provide short procedural recipes around `npm run studio:resume`, validation, local memory files, and app startup.

The verified `scripts/studio-session.js` supports `status`, `handoff`, `suspend`, and `resume`. It creates timestamped handoff files under `.agent/handoffs/`, updates `.agent/session.json`, appends to `.agent/PROJECT_LOG.md`, reads git branch/status, and summarizes corpus state from `corpus/manifest.json`.

The verified handoff file records what changed, repo state, recommended checks, reviewer starting points, and open questions.

## Pattern Lessons

- `AGENTS.md` should start with a reading order.
- A review queue gives reviewers a useful target without forcing a heavy process.
- A small session script can help when it writes human-readable handoffs and machine-readable session state.
- Project memory should include both code state and domain state. In Stem Resolver, corpus sample count and duration are part of the resumable context.
- Review should include project-memory adequacy, not just application behavior.

## Gaps Observed

The verified session state did not include a source version/date/commit for the canonical Studio Pattern because this canonical repository did not exist yet. That gap is now addressed in the templates.

## Influence On The Canonical Pattern

Stem Resolver motivates:

- `AGENTS.md` as fast orientation,
- `.agent/PROJECT_LOG.md` for durable decisions,
- `.agent/REVIEW_QUEUE.md` for reviewer focus,
- `.agent/session.json` for latest resumable state,
- `.agent/handoffs/` for cross-agent context,
- lightweight scripts only where they reduce real handoff friction.
