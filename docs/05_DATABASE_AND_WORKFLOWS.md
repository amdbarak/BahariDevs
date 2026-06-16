# 05 — Database and Workflows

## 1. Core entities

Identity:
- users
- roles/role assignments or a compact enum-based role model
- technician_profiles
- specialties
- technician_specialty

Catalogue/content:
- services
- industries
- solutions
- service_industry
- solution_service
- portfolio_projects
- blog_posts
- categories
- tags
- media
- redirects

Requests:
- service_requests
- service_request_items
- request_contacts
- request_tracking_tokens
- request_attachments
- request_status_events
- item_status_events
- request_messages
- message_attachments

Operations:
- assignments
- appointments
- service_zones
- travel_fee_rules
- completion_submissions
- completion_evidence

Commercial:
- quotes
- quote_versions
- quote_line_items
- invoices
- invoice_line_items
- external_payment_records
- receipts
- document_number_sequences

Platform:
- notifications
- provider_events
- audit_logs
- settings
- privacy_requests
- retention_runs

Codex must refine the ERD before migrations and document indexes, constraints, deletion behavior, and personal-data classification.

## 2. Request number

Format:
`BDR-{YYYY}-{six-digit sequence}`

Requirements:
- unique database constraint;
- generated transactionally;
- resets per year;
- safe under concurrent submissions;
- display identifier only.

## 3. Parent request and service items

A request is the customer-facing container. Each selected service creates a service item.

Each item may have:
- its own priority;
- delivery mode;
- schedule;
- lead/supporting technicians;
- quote lines;
- lifecycle status;
- completion submission/evidence.

The parent request presents an aggregate lifecycle. Do not let aggregate status hide incomplete items.

## 4. Item workflow

Normal states:
1. `submitted`
2. `under_review`
3. `approved`
4. `scheduled`
5. `assigned`
6. `in_progress`
7. `completion_submitted`
8. `completed`

Exceptional states:
- `on_hold`
- `rejected`
- `cancelled`
- `reopened`

### Actors
- Admin controls approval, rejection, scheduling confirmation, assignment finalization, start, hold/resume, cancellation, reopening, and completion approval.
- Technician may submit completion for an assigned in-progress item; this creates/updates evidence and requests transition to `completion_submitted`.
- Staff may draft operational changes but cannot commit restricted transitions.
- Client may send messages and accept/decline quotes through secure guest access, but cannot change operational status.

### Transition requirements
- Submitted → Under Review: admin accepts triage.
- Under Review → Approved: services/scope valid; approval note optional.
- Under Review → Rejected: reason required.
- Approved → Scheduled: confirmed appointment required unless delivery is asynchronous and schedule exemption is recorded.
- Scheduled → Assigned: lead technician required; supporting technicians optional.
- Assigned → In Progress: admin action; start timestamp.
- In Progress → Completion Submitted: assigned technician; evidence/work summary required.
- Completion Submitted → Completed: admin approval; completion timestamp.
- Completion Submitted → In Progress: admin returns for further work with reason.
- Any nonterminal operational state → On Hold: admin; reason required; previous state stored.
- On Hold → previous valid state: admin; resume note.
- Any nonterminal state → Cancelled: admin; reason required.
- Completed → Reopened: admin; reason and destination required.
  - workmanship/follow-up issue normally returns to In Progress with prior assignment;
  - scope reassessment returns to Under Review;
  - new unrelated need must become a new request.

`reopened` is an auditable event/temporary transition marker, not a state in which work remains indefinitely.

No skipping normal states except controlled admin correction/migration tooling that creates a mandatory audit record.

## 5. Parent aggregate status

The parent status is calculated from active items and exceptional conditions:
- all submitted → submitted;
- any under review while none later → under_review;
- any in progress/completion submitted → active;
- all terminal completed/cancelled/rejected → completed/closed with outcome summary;
- mixed states display `partially_completed` or `active` as defined in the UI.

Store a normalized aggregate status for querying, but recalculate through a single service after item transitions.

## 6. Assignments

- Each item has at most one active lead assignment.
- Supporting assignments may be multiple.
- Reassignment closes the prior assignment; history remains.
- Assignment requires technician role and matching active account.
- Speciality mismatch warns admin but does not automatically block unless configured.
- Technicians see only active/historical items assigned to them, with minimum necessary client data.
- No automatic assignment in v1.

## 7. Scheduling

Appointment fields:
- request item;
- delivery mode;
- requested vs confirmed status;
- start/end in UTC;
- display in `Africa/Dar_es_Salaam`;
- service location or remote details;
- service zone;
- travel fee snapshot;
- notes;
- cancellation/reschedule metadata.

Rules:
- admin confirms appointments;
- public selectable slots are admin-configured capacity windows, not direct technician assignment;
- conflict check prevents overlapping active appointments for any assigned technician;
- database/application locking prevents race conditions;
- Monday–Friday 08:00–18:00 is default business availability;
- admin may override hours with a reason;
- no technician self-managed availability calendar in v1.

## 8. Messages

Types:
- `public_message`
- `internal_note`
- `technician_work_note`
- `system_event`

Visibility:
- clients see public messages and selected system events;
- staff/admin see all;
- technicians see public messages relevant to assignments, their allowed work notes, and operational context;
- internal notes never leave the application.

Messages are append-only by default. Corrections use redaction/version/audit behavior, not silent editing.

## 9. Tracking tokens

- random 256-bit or equivalent token;
- store hash and metadata;
- expiration may be long-lived until request retention/closure but token remains revocable;
- regenerate on request;
- optional one-time email challenge for commercial acceptance or sensitive download;
- audit successful and failed access without storing raw token.

## 10. Retention resolution

The requested one-month retention is unsafe if applied uniformly to operational, audit, and financial records.

Adopt:
- request attachments and completion media: purge 30 days after final closure unless legal hold, dispute, warranty, accepted contract, or explicit retention basis applies;
- guest tracking tokens: revoke at final purge;
- request metadata/messages: retain for 24 months by default, then anonymize or delete according to approved policy;
- audit logs: retain at least 24 months;
- quotes/invoices/receipts/payment records: retain according to applicable Tanzanian tax/accounting obligations; exact period requires legal/accounting approval before launch;
- privacy export files: purge after 7 days;
- rejected spam/abusive submissions: short retention.

This is a risk-control decision and must be approved before the retention task is implemented.

## 11. Financial integrity

- Issued documents use immutable snapshots.
- Number sequences are concurrency-safe.
- Monetary values use integer minor units or fixed decimal with explicit currency.
- Never use floating-point money.
- Taxes are configurable, not assumed.
- Receipt issuance from manual external payment records is not an online payment feature.
- TRA/EFD compliance is a separate verified integration decision.
