# Warehouse Case Study

This case study is based only on files verified locally under `/Users/arnegleason/code/github.com/arnegleason/warehouse`.

## Verified Files

- `comparison/agents.md`
- `comparison/LOCAL_DEV_NOTES.md`
- `comparison/.agent/workflows/resume.md`
- `comparison/.agent/workflows/suspend.md`
- `comparison/session_manager.js`
- `comparison/server/session.json`
- `.agent/workflows/deploy_to_cloud_run.md`

## What Warehouse Shows

Warehouse appears to be an early source of the pattern's practical memory habit.

The verified `comparison/agents.md` file tells AI agents to read and update `comparison/LOCAL_DEV_NOTES.md`. It frames that file as a cheat sheet and memory bank for commands, URLs, deployment procedures, and troubleshooting details that should not be rediscovered.

The verified `comparison/LOCAL_DEV_NOTES.md` records local operational knowledge, including:

- how to run a Cloudflare MCP tunnel,
- the public MCP URL and endpoint,
- the local target port,
- instructions to generate a fresh MCP access key for external agents,
- Fly.io deployment reminders,
- a warning that deployment currently wipes the SQLite database.

The verified suspend/resume workflows are more runtime-state oriented than the later `stem-resolver` adaptation. `comparison/.agent/workflows/suspend.md` instructs the agent to run `node session_manager.js suspend "[Task Name]"`, stop running server/client processes, and report a resume phrase. `comparison/.agent/workflows/resume.md` instructs the agent to run `node session_manager.js resume`, start server and client processes, inspect logs if needed, and summarize the last task.

The verified `comparison/session_manager.js` implements that workflow by:

- backing up `server/warehouse.db` into `.backups/` during suspend,
- writing `server/session.json` with `lastTask`, `timestamp`, and `backupFile`,
- attempting a git add and commit during suspend,
- restoring the database backup during resume,
- starting backend and frontend processes,
- reporting that the app should be available at `http://localhost:3010`.

The verified `comparison/server/session.json` records a last task of `Pick/Pack/Ship Implementation` and a database backup filename.

The verified root `.agent/workflows/deploy_to_cloud_run.md` records a deployment workflow and warns that Cloud Run local file storage is ephemeral, making SQLite persistence unsafe without a future Cloud SQL or Cloud Storage solution.

## Pattern Lessons

- Local developer notes are valuable when they capture operational facts that are easy to forget and costly to rediscover.
- Suspend/resume may need to snapshot real runtime state, not just written context.
- Workflows should include warnings about data persistence and deployment risk.
- Agent instructions should explicitly tell agents when to update memory, not only when to read it.

## Gaps Observed

Within the inspected Warehouse paths, I did not verify a project log, review queue, handoff directory, or canonical `AGENTS.md` at the repository root. The useful pattern pieces are present, but they are more local and operational than the later `stem-resolver` version.

## Influence On The Canonical Pattern

Warehouse motivates:

- `LOCAL_DEV_NOTES.md` as a durable local memory surface,
- `.agent/workflows/` for reusable procedures,
- suspend/resume workflows that can preserve project-specific state,
- explicit data-persistence warnings in project memory.
