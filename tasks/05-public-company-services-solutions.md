# Task 05 — Company, services, solutions, and industries pages

## Objective
Implement the core public information architecture and service discovery journeys.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- About page with content gates
- service catalogue and detail templates
- solutions index/details
- industries index/details
- related-content links
- pricing modes

## Non-goals
- No fake founder story/projects/testimonials
- No thin location doorway pages

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Every service has unique structure and CTA
- Solutions/industries avoid duplicate boilerplate
- CMS/data source is structured for later editing
- Breadcrumbs and metadata work

## Validation
- Routes and render tests
- slug/404 tests
- pricing visibility tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after page/content review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
