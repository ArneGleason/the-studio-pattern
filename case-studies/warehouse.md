# Warehouse Case Study

This case study began from files verified locally under `/Users/arnegleason/code/github.com/arnegleason/warehouse`. Later dated field notes may also cite specific review loops, handoffs, or linked branch evidence when those sources are named in the note.

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

This script is a Warehouse-specific implementation example, not a canonical Studio Pattern requirement. It shows that some projects need suspend/resume to preserve runtime state, but other projects may use simpler written handoffs, shell workflows, or no custom script at all.

The verified `comparison/server/session.json` records a last task of `Pick/Pack/Ship Implementation` and a database backup filename.

The verified root `.agent/workflows/deploy_to_cloud_run.md` records a deployment workflow and warns that Cloud Run local file storage is ephemeral, making SQLite persistence unsafe without a future Cloud SQL or Cloud Storage solution.

## Pattern Lessons

- Local developer notes are valuable when they capture operational facts that are easy to forget and costly to rediscover.
- Suspend/resume may need to snapshot real runtime state, not just written context.
- Script-backed suspend/resume is optional and project-specific; the canonical pattern owns the intent, not a required implementation mechanism.
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

## 2026-05-11 Field Note: Picking-Basic Review Loop

Source context: Warehouse Picking-Basic Phase 1 review loop, including Arne-mediated pass-backs between Antigravity as lead developer and Codex as reviewer, plus Codex static review of `origin/feature/picking-basic-phase1` through commit `1d9db75`.

### What Worked

- Role separation helped. The lead developer could focus on implementation while the reviewer found product and state-model risks, including duplicate SKU aggregation, allocation boundaries, stale state sequencing, and scan-identifier parity with legacy Pick & Pack.
- Human-mediated relay worked as an intentional checkpoint. Arne read each pass-back, corrected role and source-context drift, and stayed mentally engaged with the implementation as it evolved rather than receiving only an end-state summary.
- Traceability headers made review cycles portable. `To`, `From`, `Created`, `Origin`, and `Subject` fields helped messages move between agents, machines, and repository contexts without losing the active branch or commit.
- P1/P2/P3 severity labels gave the lead a practical repair order and made re-review closure easier.

### Friction Observed

- Handoff source state lagged behind implementation state. A later fix summary could supersede older handoff text while the older text still remained in the message.
- The first review cycle was slowed by branch visibility and source availability checks. Requirements, local checkout state, and remote branch state need to be explicit before review begins.
- Review attention was spent on hygiene issues such as `.DS_Store`, local database files, version artifacts, trailing whitespace, and missing build-command details.
- Build and install quirks should be recorded locally. The Warehouse-specific `npm install --legacy-peer-deps` requirement belongs in Warehouse memory, while the canonical lesson is to include exact validation commands in handoffs.

### Pattern Changes Supported

- Add a role and action boundary to handoffs, especially `Reviewer` versus `Lead developer`.
- Add an explicit review-target block with repo, branch, commit, base, PR or compare URL, requirements source, and local checkout status.
- Treat the initial implementation handoff like a PR description. Later iterations can use commit SHAs and concise pass-back notes instead of rewriting the whole handoff for every small fix.
- Add a pre-handoff hygiene checklist covering `git status`, `git diff --check`, diff scope, generated artifacts, local database files, and exact validation commands.
- Add mid-project retrospectives as field evidence, with separate human, lead, and reviewer perspectives.

### Boundary Note

The React Context staleness issues, Warehouse allocation rules, duplicate SKU behavior, and `npm install --legacy-peer-deps` detail are Warehouse-specific. The reusable Studio Pattern lesson is about how handoffs make those issues visible, how reviewers verify fixes against exact commits, and how the human context steward remains engaged between cycles.
