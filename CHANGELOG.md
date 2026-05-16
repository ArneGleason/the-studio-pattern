# Changelog

## 2026-05-16

- Clarified intentional model/tool diversity as a core Studio Pattern design principle.
- Added guidance that the human owner remains the default routing hub and direct self-orchestration should be explicit delegation.
- Updated adoption guidance so projects record the intended participant mix before adding more agents.

## 2026-05-11

- Added Warehouse Picking-Basic Phase 1 as a mid-project field note for lead/reviewer collaboration, human-mediated relay, and review-loop hygiene.
- Added role/action boundaries and explicit review-target fields to handoff guidance.
- Added review preflight and closure guidance for verifying fixes against named commits or artifacts.
- Added mid-project retrospective guidance to the contribution loop.
- Expanded handoff and cross-project feedback templates with review-target hygiene and mid-project retrospective prompts.
- Tightened `Before Handoff` hygiene after Antigravity review: avoidable local artifacts and whitespace should be removed from the review diff, not merely noted.
- Clarified that Warehouse's `session_manager.js` is a project-specific suspend/resume example, not a canonical requirement.

## 2026-05-09

- Created the initial canonical Studio Pattern scaffold.
- Added core docs for roles, project memory, handoff, review, adoption, and contribution.
- Added copyable templates for `AGENTS.md`, `LOCAL_DEV_NOTES.md`, `.agent/PROJECT_LOG.md`, `.agent/REVIEW_QUEUE.md`, `.agent/session.json`, and resume/suspend workflows.
- Added verified case-study notes for `warehouse` and `stem-resolver`.
- Added `revelations.md` for recent discoveries, refinements, and working hypotheses.
- Added CC BY-SA 4.0 licensing and contribution guidance for responsible use, lineage, and field evidence.

## 2026-05-09

- Bootstrapped the canonical repository to dogfood the Studio Pattern with root memory files.
- Clarified that project memory surfaces are intended to be committed by default, with sensitive/local-only exceptions documented explicitly.
- Added cross-project boundary guidance, traceability headers, and a reusable feedback-block workflow template.
- Clarified the human-mediated relay principle: handoffs and reviews should be written for human comprehension so the stakeholder can route, correct, and enrich cross-agent work.
- Closed Antigravity sanity check for `1eac455` and aligned the cross-project feedback workflow header placeholders with the canonical traceability header.
- Added machine handles as a human-assigned convention for identifying physical/local environments separately from agent/tool names.
- Closed Antigravity review of the machine-handle convention with no actionable findings.
