# Studio Handoff: machine handle convention review

- To: `Antigravity reviewer`
- From: `Codex lead`
- To agent: `Antigravity`
- To machine: `mac-mini-pro-m4`
- From agent: `Codex`
- From machine: `macbook-pro-m5`
- Created: `2026-05-09`
- Origin: `the-studio-pattern @ a7c0245`
- Subject: Review the new machine-handle convention and dogfood usage

## Context

Arne identified an important missing distinction in the Studio Pattern: agent/tool names such as `Codex` or `Antigravity` do not identify the physical or local environment where the work is happening.

The pattern now treats machine handles as human-assigned labels for physical machines or local environments. This preserves the human-mediated relay while making distributed local checkouts visible.

Current dogfood mapping:

- Lead: `Codex` on `macbook-pro-m5`
- Reviewer: `Antigravity` on `mac-mini-pro-m4`

## Content Commit To Review

- Commit: `a7c0245`
- Title: `Add machine handle convention`
- Repository: `https://github.com/ArneGleason/the-studio-pattern`

## What Changed

- Added distributed local environment guidance to `docs/pattern-overview.md`.
- Added machine-handle rules and optional traceability fields to `docs/handoff-protocol.md`.
- Added machine-handle memory guidance to `docs/project-memory.md`.
- Added adoption guidance for naming local environments in `docs/adoption-guide.md`.
- Added environment-awareness prompts to `docs/review-protocol.md`.
- Updated templates to include `machineHandle` fields and local environment notes.
- Dogfooded this repo as `Codex` on `macbook-pro-m5`, with intended reviewer `Antigravity` on `mac-mini-pro-m4`.

## Intended Principle

Agent identity explains who is reasoning. Machine handle explains where the local checkout, dependencies, credentials, caches, hardware, and physical failure boundary live.

Machine handles should be assigned by the human relay, not inferred automatically from hostnames. OS hostnames can be recorded as non-authoritative troubleshooting details if the human maps them explicitly.

## Requested Review

Please check:

- Is the distinction between agent/tool and machine handle clear?
- Does the convention preserve human control over environment identity instead of auto-inference?
- Are the new handoff fields useful without making every local handoff too heavy?
- Does `.agent/session.json` now capture enough environment context?
- Would an adopting project know how to choose and record handles like `macbook-pro-m5` and `mac-mini-pro-m4`?
- Are there any docs/templates that still imply the agent name alone is enough identity?

## Suggested Starting Points

1. `docs/pattern-overview.md`
2. `docs/handoff-protocol.md`
3. `docs/project-memory.md`
4. `docs/adoption-guide.md`
5. `docs/review-protocol.md`
6. `templates/AGENTS.md`
7. `templates/LOCAL_DEV_NOTES.md`
8. `templates/.agent/session.json`
9. `LOCAL_DEV_NOTES.md`
10. `.agent/session.json`

## Please Report Back

A simple thumbs-up is enough if the convention is sound.

If something feels off, please report findings in severity order with file and line references where possible. Especially useful feedback would be whether machine handles should appear in more or fewer places, and whether the handle naming rules are too strict or too loose.
