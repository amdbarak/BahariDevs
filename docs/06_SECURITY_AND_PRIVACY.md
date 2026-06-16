# 06 — Security and Privacy

## 1. Standard

Apply OWASP-oriented secure design, Laravel security controls, least privilege, privacy by design, and Tanzanian legal review.

The platform processes personal data and may need data-controller/processor registration and policies under Tanzania's Personal Data Protection framework. The owner must obtain qualified legal/compliance advice; Codex must not invent compliance status.

## 2. Threat model priorities

- guessable request access / IDOR;
- malicious uploads;
- credential attacks;
- administrator account takeover;
- privilege escalation;
- exposed private documents;
- forged provider webhooks;
- notification abuse;
- stored XSS through CMS/messages;
- CSRF;
- duplicate or raced lifecycle actions;
- sensitive logs/backups;
- data retained beyond purpose;
- cross-border provider/data-transfer implications.

## 3. Authentication

- no public registration in v1;
- admin/staff/technician accounts are invited or created by admin;
- verified email required;
- strong password validation;
- login throttling by normalized identity and IP;
- admin TOTP 2FA mandatory before privileged access;
- recovery codes protected;
- password confirmation for sensitive actions;
- session regeneration on login;
- secure, HTTP-only, SameSite cookies;
- reasonable idle and absolute session timeouts;
- account disable and session revocation;
- generic password-reset/login messages to limit enumeration.

## 4. Authorization

- policies for every request, item, message, file, appointment, assignment, CMS item, commercial document, audit view, privacy request, and setting;
- authorization both in UI and server action;
- route model binding is not authorization;
- technicians access only assigned items;
- staff cannot use admin-only lifecycle/commercial actions;
- guest access is capability-token scoped;
- downloads always re-check authorization.

## 5. Files

Allowed initial types:
- JPEG, PNG, WebP;
- PDF;
- optionally HEIC only after safe server support is verified.

Controls:
- max size configured by category; initial request-file recommendation 10 MB each and 30 MB total;
- MIME sniffing plus extension allowlist;
- image decoding/re-encoding where appropriate;
- PDF treated as download by default;
- generated names;
- no executable/svg/html uploads from customers;
- private disk;
- content-disposition and nosniff headers;
- scan adapter and quarantine state, even if antivirus infrastructure is not available at initial launch;
- limits on count, dimensions, and decompression;
- authorization and audit for download/delete;
- purge jobs and backup deletion strategy.

## 6. Forms and abuse

- CSRF on browser forms;
- rate limits for contact, request submission, tracking, token regeneration, and verification codes;
- honeypot/time-to-submit or approved privacy-conscious anti-abuse controls;
- CAPTCHA only if abuse justifies it and owner approves provider/privacy impact;
- idempotency key for request submission;
- server-side validation and normalized phone/email;
- escape output by default;
- sanitize approved rich text with an allowlist;
- reject unsafe URLs/protocols.

## 7. Webhooks

- dedicated routes outside standard CSRF only where necessary;
- verify provider signature and timestamp;
- reject replay;
- store external event ID with unique constraint;
- acknowledge quickly and queue processing;
- retain redacted payload metadata, not unnecessary secrets/content;
- unknown inbound messages enter quarantine/review;
- outbound/inbound adapters have circuit-breaker/retry controls.

## 8. Audit

Audit:
- authentication and 2FA changes;
- user/role changes;
- request and item transitions;
- assignment/reassignment;
- appointments;
- messages redacted/deleted;
- file view/download/delete;
- tracking-token regeneration;
- quote/invoice/receipt lifecycle;
- settings/provider changes;
- CMS publish actions;
- exports, erasure, retention;
- security/admin overrides.

Record actor, action, subject type/id, timestamp, relevant before/after fields, reason, request/correlation ID, and appropriate network metadata. Do not log secrets or full sensitive content.

## 9. Privacy

Required capabilities:
- privacy notice and purpose disclosure;
- consent/acknowledgement records;
- transactional communication basis and channel preferences;
- data access/export request;
- correction request;
- deletion request with legal/contract exceptions;
- restriction/objection handling;
- data minimization;
- retention schedule;
- secure deletion or anonymization;
- provider/subprocessor inventory;
- breach-response procedure;
- cross-border transfer review.

## 10. Security headers and deployment

At minimum:
- HTTPS-only;
- HSTS after domain/TLS verification;
- Content-Security-Policy developed and tested;
- frame-ancestors or X-Frame-Options;
- X-Content-Type-Options;
- Referrer-Policy;
- Permissions-Policy;
- secure error handling;
- `APP_DEBUG=false` in production;
- deny access to dotfiles, storage, vendor, source maps where inappropriate, and backup files;
- health endpoint must not expose secrets.

## 11. Secrets

- environment variables or host secret controls;
- separate credentials per environment;
- least-privilege provider keys;
- key rotation documented;
- never place credentials in tickets, screenshots, fixtures, logs, prompts, or commits;
- rotate immediately if exposure is suspected.

## 12. Required launch review

Before launch:
- dependency audit;
- authorization matrix review;
- upload attack tests;
- guest-token tests;
- webhook verification tests;
- admin 2FA verification;
- TLS/header scan;
- backup confidentiality review;
- production log review;
- privacy/legal sign-off checklist;
- no known critical/high vulnerabilities.
