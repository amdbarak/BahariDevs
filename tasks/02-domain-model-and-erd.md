# Task 02 — Domain model and ERD

## Objective
Finalize the data model, personal-data classification, indexes, and migration plan before feature implementation.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- ERD and table catalogue
- Request/item, scheduling, communications, commercial, CMS, audit/privacy entities
- Keys, constraints, indexes, deletion behavior
- Data classification and retention tags
- Migration ordering

## Non-goals
- No broad UI implementation
- No provider integrations

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- ERD covers all approved v1 entities
- Every external identifier and unique sequence is defined
- Every personal-data field has purpose/retention classification
- Concurrency-sensitive constraints are documented
- Owner can review schema before migrations

## Validation
- Schema review checklist
- Migration smoke plan
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop before creating the full set of domain migrations unless explicitly approved.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
