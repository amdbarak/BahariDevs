# 02 — Architecture

## 1. Selected architecture

A **modular Laravel monolith** optimized for maintainability and cPanel-style deployment.

### Baseline
- Laravel 13
- PHP 8.4 production baseline; evaluate PHP 8.5 during hosting preflight
- MariaDB
- Blade + Livewire 4 + Alpine.js
- Tailwind CSS 4
- Vite
- Laravel Fortify through the official Livewire starter foundation
- Pest 4 preferred for feature/browser tests; remain compatible with PHPUnit 13
- database queue
- database or file cache initially; do not assume Redis
- local private storage initially, with an adapter-ready path to S3-compatible storage
- timezone `Africa/Dar_es_Salaam`
- English default locale
- TZS default currency

Laravel 13 supports PHP 8.3–8.5. PHP 8.4 is chosen as the safer shared-hosting baseline while remaining actively supported. Exact host versions and extensions must be verified before repository bootstrap.

## 2. Why Livewire

Livewire is selected because:
- the product is a server-rendered Laravel application rather than a public API-first SPA;
- public SEO and first-load reliability matter;
- admin workflows are form/table/state heavy;
- the expected team and traffic are modest;
- deployment to shared hosting is simpler;
- one PHP-centered codebase reduces operational complexity;
- reactive behavior is still available without a separate JavaScript application architecture.

Do not use React/Vue/Inertia unless a later architectural decision record demonstrates a material requirement.

## 3. Domain modules

Suggested namespace boundaries:

```text
app/
  Domain/
    Identity/
    Catalogue/
    Leads/
    ServiceRequests/
    Scheduling/
    Communications/
    Commercial/
    Content/
    Notifications/
    Audit/
    Privacy/
    Settings/
  Application/
    Actions/
    DTOs/
    Queries/
  Http/
  Livewire/
  Policies/
  Support/
```

This is not a requirement to create layers with empty abstractions. Place code where cohesion and testing are improved.

## 4. Key application services

Examples:
- `CreateGuestServiceRequest`
- `GenerateRequestBusinessNumber`
- `IssueGuestTrackingToken`
- `TransitionServiceItem`
- `RecalculateRequestAggregateStatus`
- `AssignTechnicians`
- `ScheduleAppointment`
- `SubmitCompletion`
- `ApproveCompletion`
- `PostRequestMessage`
- `CreateQuoteVersion`
- `IssueInvoice`
- `RecordExternalPayment`
- `IssueReceipt`
- `DispatchTransactionalNotification`
- `ProcessInboundProviderMessage`
- `FulfilPrivacyRequest`
- `PurgeExpiredPrivateData`

## 5. State transitions

Use explicit transition services and policies. Do not permit arbitrary status assignment from controllers or forms. Validate current state, target state, actor, required evidence/reason, and concurrency version inside a transaction.

## 6. Concurrency and idempotency

- Add optimistic locking or equivalent safeguards to lifecycle-sensitive records.
- Prevent duplicate guest submissions through idempotency keys/form tokens.
- Provider webhooks require unique external event IDs.
- Notification jobs must be retry-safe.
- Quote/invoice issuance must not create duplicate numbers.
- Scheduling checks and writes occur in one transaction where practical.

## 7. Public and private identifiers

- Sequential numbers are business display identifiers only.
- Public URLs use ULID/UUID plus high-entropy access capability or signed links.
- Internal numeric primary keys may be used in the database but are not exposed.
- Tokens are revocable and rotated after suspected disclosure.

## 8. File architecture

Disks:
- `public_media`: approved marketing/CMS assets intended for public delivery;
- `private_requests`: customer attachments and request evidence;
- `private_exports`: privacy exports and generated sensitive documents.

Private files:
- live outside public web root;
- use generated storage names;
- preserve original names in metadata;
- are downloaded through authorized controllers;
- support response headers preventing unsafe inline execution;
- are included in backup and purge policies.

## 9. Queue and scheduler

Default to the database queue because Redis and persistent workers are unverified.

Preferred production:
- persistent `queue:work` under a process manager, if supported.

Shared-hosting fallback:
- cron every minute invoking Laravel scheduler;
- scheduler launches bounded queue work with stop/time limits;
- failed jobs are retained and visible to admin;
- health monitoring detects stalled processing.

Do not use the synchronous queue in production for provider webhooks or user-facing notification reliability.

## 10. Communications adapters

Define provider-neutral interfaces:
- `OutboundEmailGateway`
- `OutboundWhatsAppGateway`
- `InboundMessageNormalizer`

Preferred:
- email: Mailgun when credentials/domain validation are available; SMTP fallback via configuration;
- WhatsApp: Meta WhatsApp Cloud API;
- adapters must be replaceable without changing request-domain code.

Inbound replies:
- verify webhook/provider signatures;
- map provider conversation identifiers to request threads;
- quarantine unmatched or unsafe messages for admin review;
- strip/normalize HTML;
- scan/validate attachments;
- prevent external messages from becoming internal notes.

## 11. Authentication and roles

Roles:
- `admin`
- `staff`
- `technician`
- future `client` reserved but not enabled in v1

Use policies rather than scattered role string checks. Admin 2FA is mandatory. Public registration is disabled.

## 12. Observability

Use structured application logs with request/correlation IDs. Keep business audit logs separate from runtime logs. Never store secrets or sensitive message/file contents in runtime logs.

## 13. Architectural decision records

Material changes require a short ADR under `docs/adr/`:
- context;
- decision;
- alternatives;
- consequences;
- date and owner approval.
