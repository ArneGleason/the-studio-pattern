# Instructions for AI Agents

Welcome to The Studio Pattern.

This repository is the canonical home for the Studio Pattern: a lightweight working method for coordinating human direction, lead agents, reviewer agents, and specialist agents across software and research projects.

This repo now dogfoods the pattern. Treat root-level memory files as the project memory for evolving the pattern itself, while `templates/` remains the copyable starter kit for adopting projects.

## Studio Pattern Source

- Canonical repository: https://github.com/ArneGleason/the-studio-pattern
- Self-hosting baseline commit: `0890aa4`
- Source date: 2026-05-09
- Local adaptation: canonical pattern meta-development, documentation review, template evolution, and case-study maintenance.

## First Reads

1. Read `README.md` for the mission and repository map.
2. Read `docs/pattern-overview.md` for the core pattern.
3. Read `docs/project-memory.md` for memory surface expectations.
4. Read `LOCAL_DEV_NOTES.md` for local workflow notes.
5. Check `.agent/PROJECT_LOG.md` and `.agent/REVIEW_QUEUE.md` for current work and review focus.
6. If resuming or reviewing, read `.agent/session.json` and the latest handoff under `.agent/handoffs/`.

## Working Rules

- Keep the pattern lightweight and evidence-based.
- Prefer changes that help real projects resume, hand off, or review work with less confusion.
- Distinguish canonical guidance from project-specific adaptation.
- Update `templates/` only when a practice should be reusable by new projects.
- Update case studies only from verified local files or linked public evidence.
- Update `revelations.md` for working hypotheses that are not ready to become canonical docs.
- Update `.agent/PROJECT_LOG.md` when changing the pattern's structure, templates, or protocols.
- Update `.agent/REVIEW_QUEUE.md` when leaving questions for another reviewer.

## Validation

This is a docs-first repository. Before handoff, run at least:

```sh
git status --short
find . -path ./.git -prune -o -maxdepth 3 -type f -print | sort
```

Also inspect changed Markdown for broken links, stale placeholders, or unclear adoption instructions.

## Project Safety

Do not put secrets, credentials, private project data, or sensitive conversation logs in canonical pattern files. Root `.agent/` files are intended to be committed, so keep them suitable for repository history.
