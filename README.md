# The Studio Pattern

The Studio Pattern is a lightweight working method for coordinating human direction, lead developer agents, reviewer agents, and specialist models across software and research projects.

The goal is not to create a rigid framework. The goal is to keep a clear, evolving, evidence-based playbook for preserving context, handing off work, reviewing decisions, and carrying lessons from one project back into the shared method.

This repository is the canonical home for the pattern. Individual projects copy and adapt the templates here, keep their own local `.agent/` memory, and report useful improvements back.

## Current State

This is an early canonical version created from local evidence in two sibling repositories:

- `warehouse`, which contains an earlier agent-instruction and suspend/resume workflow around local development state.
- `stem-resolver`, which contains a newer adaptation with `AGENTS.md`, `LOCAL_DEV_NOTES.md`, project memory files, handoff notes, and a small session script.

The pattern should be treated as working practice, not doctrine. Each project that uses it is both a consumer and a field test.

## Read This First

If you are a new agent or human entering this repository:

1. Read [AGENTS.md](AGENTS.md) for repo-specific working rules and current memory surfaces.
2. Read this `README.md`.
3. Read [docs/pattern-overview.md](docs/pattern-overview.md).
4. Read [docs/project-memory.md](docs/project-memory.md).
5. If adopting the pattern, follow [docs/adoption-guide.md](docs/adoption-guide.md).
6. If reviewing or handing off work, read [docs/handoff-protocol.md](docs/handoff-protocol.md) and [docs/review-protocol.md](docs/review-protocol.md).
7. Check [revelations.md](revelations.md) for recent discoveries and working hypotheses.

## Core Idea

A project using the Studio Pattern keeps a small set of practical memory surfaces:

- `AGENTS.md` gives new agents fast orientation.
- `LOCAL_DEV_NOTES.md` records commands, ports, setup notes, and recurring gotchas.
- `.agent/PROJECT_LOG.md` records durable decisions and meaningful project events.
- `.agent/REVIEW_QUEUE.md` records questions and risks for reviewer attention.
- `.agent/session.json` records the latest machine-readable session state.
- `.agent/handoffs/` stores timestamped notes for cross-agent or cross-environment handoff.
- `.agent/workflows/` stores short resume/suspend procedures.

The human sets direction and taste. The lead agent moves the project forward and records what matters. The reviewer agent examines the result from a fresh angle. Specialist agents can be brought in for narrow tasks when useful.

## How Projects Use The Pattern

Copy the relevant templates from `templates/` into the project:

```sh
cp templates/AGENTS.md /path/to/project/AGENTS.md
cp templates/LOCAL_DEV_NOTES.md /path/to/project/LOCAL_DEV_NOTES.md
cp -R templates/.agent /path/to/project/.agent
```

Then adapt them locally. A project should record the source it adopted from:

```md
Studio Pattern: 2026-05-09 initial canonical scaffold
Source: the-studio-pattern commit <commit-sha-or-date>
License: CC BY-SA 4.0
Local adaptation: <what changed for this project>
```

Do not use git submodules yet. The intended flow is copy, adapt, run in the field, and bring back improvements through ordinary docs changes or pull requests.

## How Projects Contribute Back

When a project discovers a better practice, it should capture the local evidence first:

- What problem occurred?
- Which file or workflow caught it, or failed to catch it?
- What small change improved the next session, review, or handoff?
- Is the improvement project-specific, or should it become canonical?

Reusable improvements should be proposed back here by updating docs, templates, case studies, or [revelations.md](revelations.md). See [docs/contribution-loop.md](docs/contribution-loop.md).

## Design Principles

- The central repo is the source of truth for the shared pattern.
- Project repos keep their own adapted local `.agent/` files.
- Prefer practical memory surfaces over elaborate process.
- Make the first reads obvious.
- Keep handoffs short enough that another agent will actually read them.
- Make decisions visible where future work will look for them.
- Treat reviews as a way to find bugs, risks, unclear memory, and weak assumptions.
- Let field evidence change the pattern.

## Repository Map

- `docs/`: canonical explanation of the pattern.
- `templates/`: copyable starter files for adopting projects.
- `case-studies/`: notes from verified local project evidence.
- `revelations.md`: recent discoveries, refinements, and working hypotheses.
- `CHANGELOG.md`: history of canonical pattern changes.
- `CONTRIBUTING.md`: contribution norms, responsible-use expectations, and lineage guidance.
- `LICENSE`: CC BY-SA 4.0 license text.

## License

The Studio Pattern is licensed under [CC BY-SA 4.0](LICENSE). You can share and adapt it, including commercially, as long as you preserve attribution and share adaptations under the same license.

The project also asks adopters to keep a small lineage note pointing back to this repository so the evolution of the pattern can be studied over time.

Suggested attribution: `The Studio Pattern by Arne Gleason, licensed CC BY-SA 4.0, https://github.com/ArneGleason/the-studio-pattern`.

## Status

Version: initial canonical scaffold, dated 2026-05-09.

This repository should evolve after real use, especially after a lead/reviewer cycle exposes which files were helpful, which were ignored, and which questions repeated across projects.
