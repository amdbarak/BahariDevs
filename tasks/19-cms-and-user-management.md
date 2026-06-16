# Task 19 — CMS and user management

## Objective
Complete controlled content publishing and internal user administration.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Users/disable/reset/roles
- technician specialties
- blog/portfolio/service CMS
- SEO fields
- media
- preview/scheduling
- redirects

## Non-goals
- No client accounts
- No fabricated content

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Publication gates and permissions work
- scheduled content depends on monitored scheduler
- unsafe HTML blocked
- role changes audited
- deleted user behavior defined

## Validation
- CMS authorization/publication tests
- sanitization tests
- user lifecycle tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after content workflow review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
