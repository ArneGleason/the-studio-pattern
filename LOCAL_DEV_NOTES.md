# Local Developer Notes

This is the living workflow memory for developing the canonical Studio Pattern repository.

## Repository

- GitHub: https://github.com/ArneGleason/the-studio-pattern
- Default branch: `main`
- Current role of this repo: canonical pattern source and self-hosting field test.

## Studio Pattern Source

- Canonical repository: self, `https://github.com/ArneGleason/the-studio-pattern`
- Self-hosting baseline commit: `0890aa4`
- Source date: 2026-05-09
- Local adaptation: meta-development of the pattern itself.

## Local Environment

- Machine handle: `macbook-pro-m5`
- Display label: MacBook Pro M5
- Primary agent/tool here: `Codex`
- Local checkout: `/Users/arnegleason/code/github.com/arnegleason/the-studio-pattern`
- Current reviewer environment: `Antigravity` on `mac-mini-pro-m4`

Machine handles are human-assigned Studio Pattern labels. They are not automatically derived from OS hostname, username, serial number, or network name. If a hostname is useful for troubleshooting, record it as a non-authoritative mapping after Arne confirms it.

## Common Checks

List files:

```sh
find . -path ./.git -prune -o -maxdepth 3 -type f -print | sort
```

Check git state:

```sh
git status --short
```

Review recent history:

```sh
git log --oneline --decorate -5
```

Search for placeholders before release-like handoff:

```sh
rg -n "TODO|FIXME|<[^>]+>|placeholder|path/to/project" .
```

## Version Control Strategy

The root `.agent/` directory is intentionally committed in this repository. It is part of the self-hosting evidence for the pattern.

For adopting projects, the default recommendation is also to commit `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` memory surfaces so project context travels across machines and agents. Project-specific secrets, raw logs, large generated files, local databases, or private data should be excluded explicitly.

## Current Review Context

Antigravity reviewed the canonical repo on 2026-05-09 and raised two main findings:

- P1: the canonical repo should dogfood the pattern with root `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` files.
- P2: docs should clarify whether `.agent/` files are committed.
