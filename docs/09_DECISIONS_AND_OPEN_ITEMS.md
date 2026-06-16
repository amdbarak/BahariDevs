# 09 — Decisions and Open Items

## 1. Resolved decisions

| Area | Decision |
|---|---|
| Product name | BahariDevs Limited |
| Primary outcome | Qualified leads |
| Architecture | Laravel modular monolith |
| Frontend | Blade + Livewire 4 + Alpine.js |
| CSS | Tailwind CSS 4 |
| Framework | Laravel 13, after host preflight |
| PHP | 8.4 baseline; 8.5 only after verified compatibility |
| Database | MariaDB |
| Theme | Dark default, light toggle |
| Language | English v1; translation-ready for Kiswahili |
| Client access | Guest submission/tracking; no client accounts v1 |
| Tracking | Sequential business number plus separate high-entropy token |
| Assignments | One lead plus supporting technicians per item |
| Workflow control | Admin-controlled; technician submits completion |
| Scheduling | Requested/configured slots plus admin confirmation |
| Queue | Database by default; shared-hosting cron fallback |
| Email | Provider adapter; Mailgun preferred if verified |
| WhatsApp | Provider adapter; Meta Cloud API preferred |
| Files | Private customer storage; public CMS storage separate |
| Payments | No online gateway; optional manual external-payment record for receipt |
| Portfolio privacy | Named, anonymous, or private/unpublished modes |
| Admin security | Mandatory TOTP 2FA |
| Analytics | Provider-neutral and consent-aware |
| Geographic design | No Zanzibar visual theme |

## 2. Professional resolution of ambiguous items

### Visual styles to avoid
Generic neon/cyber clichés, excessive glassmorphism, stock “hacker” imagery, motion-heavy agency imitation, and fake proof.

### Guest tracking
Secure random capability link, hashed token storage, rate limiting, revocation, and optional email challenge for sensitive actions.

### Workflow
Item-level strict workflow with completion submission and admin approval, plus on-hold, rejected, cancelled, and audited reopening.

### Notifications
Send meaningful lifecycle/commercial changes, never internal notes, and no WhatsApp notification merely for uploads.

### Portfolio confidentiality
Explicit publication mode with anonymization and client approval metadata.

## 3. Open launch blockers requiring owner or vendor input

- actual logo/brand-guideline files must be placed in repository-approved asset location;
- Satoshi licence/font files, or approval to launch with system fallback;
- real company copy and verified address/contact details;
- founder biography and message;
- real project/case-study evidence;
- testimonials and permissions;
- company registration/tax information where displayed;
- approved response-time wording;
- service pricing mode/value for every service;
- service zones and fee rules;
- tax/VAT configuration;
- legal review of privacy, terms, retention, and receipts;
- whether BahariDevs must register with Tanzania PDPC as controller/processor;
- Mailgun/domain credentials or alternate SMTP;
- Meta WhatsApp business/app/template approval;
- hosting PHP/MariaDB/extensions/cron/worker/document-root verification;
- staging environment;
- backup destination;
- monitoring/alert destination;
- domain and DNS access.

## 4. Retention conflict

The owner answered “one month” for both request records and attachments. Applying that literally would undermine audits, disputes, warranty history, quotes/invoices/receipts, and potential statutory duties.

The specification therefore proposes:
- 30 days after closure for attachments by default;
- 24 months for operational metadata/audit;
- legally required period for financial records.

This must be explicitly approved before Task 21.

## 5. Commercial/legal caveat

A generated “receipt” is not automatically a legally compliant Tanzanian fiscal receipt. TRA/EFD requirements, tax registration, numbering, and document wording require accounting/legal confirmation. The v1 system must label documents accurately and avoid implying an unverified fiscal integration.

## 6. Source/version reference date

Technical baseline checked on 15 June 2026:
- Laravel 13 released 17 March 2026 and supports PHP 8.3–8.5.
- PHP 8.4 and 8.5 are supported branches.
- official Laravel Livewire starter uses Livewire 4 and Tailwind.
- HostPinnacle publishes cPanel cron guidance and a 35 GB NVMe shared plan, but account-specific capabilities remain unverified.
