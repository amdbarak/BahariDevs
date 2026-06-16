# Task 06 — Portfolio, blog, contact, and legal surfaces

## Objective
Complete remaining public templates and safe content-management foundations.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Portfolio modes and templates
- blog listing/article/categories/tags
- contact form
- privacy/terms/accessibility/cookie drafts
- custom errors
- publication states

## Non-goals
- No real legal compliance claim
- No public fake case studies/testimonials

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Draft/scheduled/private content is inaccessible to search/public users
- Rich content is sanitized
- Contact form is validated/rate-limited/audited as appropriate
- Anonymous portfolio hides client identifiers

## Validation
- Publication authorization tests
- sanitization tests
- contact abuse/validation tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after owner review and legal-content caveat confirmation.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
