# Task 18 — Admin request operations

## Objective
Deliver the integrated admin workspace for triage, workflow, assignments, schedules, messages, files, and commercial context.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Dashboard queues
- filters/search/pagination
- request detail command UI
- bulk actions only where safe
- attention indicators
- export controls

## Non-goals
- No destructive unaudited bulk status changes

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Every command uses domain service/policy
- large lists paginated
- empty/error/loading states
- sensitive exports authorized and audited

## Validation
- Livewire/admin feature tests
- policy tests
- query/N+1 review
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after administrator usability review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
