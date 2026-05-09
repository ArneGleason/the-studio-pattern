# Cross-Project Feedback: project boundary guidance

- To: `the-studio-pattern`
- From: `Arne, coordinating between stem-resolver and the-studio-pattern`
- Created: `2026-05-09`
- Origin: Stem Resolver working thread, after Studio Pattern bootstrap work
- Subject: Clarifying project boundaries after cross-project bootstrap work

## Context

The `stem-resolver` work created and adopted a local Studio Pattern layer, then led to creating `the-studio-pattern` as the canonical repository. Because the efforts were tightly connected, some canonical pattern work was coordinated from the Stem Resolver thread.

Going forward, canonical pattern evolution should happen in `the-studio-pattern`, while Stem Resolver should remain focused on the AI-audio corpus/catalog tool and its local adaptation of the pattern.

## Local Evidence

- `the-studio-pattern @ 74759a9`: canonical repo has root `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` memory files.
- `stem-resolver @ 1b531fe`: adopting project links back to the canonical pattern.
- The clarification itself used a `To` / `From` / `Created` / `Origin` / `Subject` traceability header.

## Canonical Decision

- Document project boundaries in the contribution and adoption flows.
- Add a standard cross-project feedback block for lessons moving from adopting projects back to the canonical pattern.
- Treat traceability headers as recommended only when context crosses project, repository, or thread boundaries.

## Boundary Note

Stem Resolver-specific product work, corpus tooling, local commands, and review findings remain in `stem-resolver`. Reusable pattern lessons may be summarized here after they are recorded locally first.

## Reviewer Follow-Up

- Check whether the feedback block is lightweight enough.
- Check whether traceability headers are clear without becoming mandatory ceremony for ordinary local handoffs.
