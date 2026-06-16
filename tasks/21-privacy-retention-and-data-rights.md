# Task 21 — Privacy, retention, and data rights

## Objective
Implement approved retention, export, correction, deletion, restriction, and legal-hold processes.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Privacy requests
- identity verification
- export
- anonymize/delete
- attachment purge
- legal hold
- retention scheduler
- subprocessor inventory fields

## Non-goals
- Do not implement disputed retention period without owner approval
- No deletion that breaks required financial/audit obligations

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Retention policy approved
- exports scoped correctly
- purge idempotent
- legal holds respected
- backups limitation documented
- all actions audited

## Validation
- Privacy authorization tests
- export isolation tests
- retention clock tests
- legal-hold tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after owner/legal review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
