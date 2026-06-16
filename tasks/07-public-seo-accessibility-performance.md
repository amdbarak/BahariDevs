# Task 07 — Public SEO, accessibility, and performance release gate

## Objective
Audit and harden the public website for the marketing release.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Sitemap/robots/canonical
- structured data with verified fields only
- redirect system
- image optimization
- cache strategy
- WCAG audit
- performance budget
- analytics abstraction without unapproved provider

## Non-goals
- No marketing analytics cookies without approval
- No operational app features

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Public acceptance checklist passes
- No serious/critical automated accessibility findings
- Representative performance targets are met or deviations documented
- Search controls prevent indexing sensitive/draft routes

## Validation
- SEO tests
- accessibility checks
- Lighthouse/manual evidence
- cache/redirect tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop at the marketing-release approval gate.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
