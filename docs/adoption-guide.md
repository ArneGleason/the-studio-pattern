# Adoption Guide

This guide helps a project start using the Studio Pattern without turning it into ceremony.

## 1. Copy The Templates

From this repository:

```sh
cp templates/AGENTS.md /path/to/project/AGENTS.md
cp templates/LOCAL_DEV_NOTES.md /path/to/project/LOCAL_DEV_NOTES.md
cp -R templates/.agent /path/to/project/.agent
```

## 2. Record The Source

In the adopted `AGENTS.md` and `.agent/session.json`, record:

- Studio Pattern version or date,
- source repository,
- source commit if known,
- local adaptation notes.

Example:

```md
Studio Pattern: 2026-05-09 initial canonical scaffold
Source: the-studio-pattern commit <commit-sha>
License: CC BY-SA 4.0
Local adaptation: Added corpus validation and audio storage policy.
```

## 3. Fill The First Reads

Edit `AGENTS.md` so a new agent knows exactly what to read first.

The first-read list should usually include:

- project README,
- local developer notes,
- project-specific Studio Pattern notes if any,
- project log,
- review queue,
- latest handoff when present.

## 4. Fill Local Commands

Edit `LOCAL_DEV_NOTES.md` with the commands that matter:

- install,
- run,
- validate,
- test,
- lint,
- deploy,
- local URLs,
- known gotchas.

## 5. Start The Logs Lightly

Create one entry in `.agent/PROJECT_LOG.md` for adoption:

```md
## <date>

- Adopted the Studio Pattern from <source>.
- Local memory surfaces: `AGENTS.md`, `LOCAL_DEV_NOTES.md`, `.agent/`.
- Initial reviewer focus: see `.agent/REVIEW_QUEUE.md`.
```

## 6. Decide Whether A Script Is Needed

Do not add automation until it saves real effort.

A project may need a small session script if it must:

- snapshot runtime state,
- generate handoff files,
- summarize dataset or corpus state,
- restore a local database,
- print current status for a future session.

The canonical requirement is not the script. The requirement is that future work can resume accurately.

## 7. Run One Lead/Review Cycle

The first real test is simple:

1. Lead agent completes a coherent task.
2. Lead updates memory surfaces.
3. Lead creates a handoff.
4. Reviewer starts only from the documented first reads.
5. Reviewer records what was missing or confusing.
6. Useful lessons are folded back into the project and, if reusable, proposed here.
