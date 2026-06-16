# 01 — Product Requirements

## 1. Success outcomes

### Primary
Increase qualified service enquiries from relevant organizations and customers.

### Secondary
- Reduce uncertainty before a customer contacts BahariDevs.
- Capture complete request information once.
- Provide trustworthy request tracking.
- Give the administrator full operational oversight.
- Make assignments, schedules, communication, commercial documents, and completion evidence traceable.

## 2. Suggested launch metrics

Measure only after analytics consent/configuration is approved:
- qualified enquiry conversion rate;
- request form completion rate;
- abandonment by step;
- source/landing page of qualified enquiries;
- median first-response time;
- percentage of requests with complete intake data;
- percentage completed without off-platform status confusion;
- notification delivery success rate;
- page performance and accessibility regressions.

Do not define arbitrary performance claims as public marketing copy.

## 3. Personas

### Prospective decision-maker
A manager or procurement stakeholder evaluating competence, reliability, scope, and evidence.

### Small-business owner
Needs understandable service options, fast contact, transparent next steps, and proportionate pricing.

### Guest client
Submits and tracks work without creating an account.

### Administrator
Controls status, assignments, schedules, content, commercial documents, and settings.

### Staff member
Assists operations, communicates internally, prepares drafts, but cannot perform restricted state changes or final assignments.

### Technician
Sees assigned service items, appointment details, customer-safe information, work notes, and evidence actions. Cannot approve completion or freely alter lifecycle state.

## 4. Public user journeys

### Discover and enquire
Landing page → relevant service/industry/solution → evidence/FAQ → request or contact CTA.

### Request service
Choose services → provide contact and location → describe need and priority → propose date/slot → upload valid files → consent → submit → receive secure tracking link.

### Track request
Open secure signed/tokenized link → verify access if risk controls require it → view safe status timeline, appointments, assigned technician names, public messages, quote/invoice status, and completion evidence intended for the client.

## 5. Request intake requirements

Required unless marked conditional:
- full name;
- organization/business name (optional for individuals);
- email;
- Tanzanian/international phone with country code;
- WhatsApp indicator;
- physical/service location;
- preferred contact method;
- one or more services;
- detailed problem/goal;
- priority requested by client;
- delivery preference;
- preferred date/time window or configured slot;
- private attachments;
- privacy acknowledgement;
- consent to transactional communications.

Emergency is a requested priority, not a guaranteed emergency-response service. Admin may reclassify priority with an audit reason.

## 6. Guest tracking

- Generate a human-readable business number such as `BDR-2026-000001`.
- Generate a separate high-entropy random access token.
- Store only a cryptographic hash of the raw token where feasible.
- Send the raw token only through the initial secure link.
- Allow admin revocation/regeneration.
- Apply rate limiting.
- Never reveal whether a request exists through an unauthenticated ID-only lookup.
- Sensitive actions may require a one-time email verification challenge.
- Do not expose internal IDs.

## 7. Service catalogue

Initial services:
- Systems Development
- Web Development
- UI/UX Design
- Branding
- CCTV Installation
- Networking
- IT Support
- Cybersecurity
- Server Setup
- Cloud & Email Setup
- POS Systems
- Access Control Systems
- Biometric Systems
- WiFi Optimization

Each service supports:
- summary and full description;
- customer problems/use cases;
- benefits/outcomes;
- suitable industries;
- delivery modes;
- public pricing mode: exact, starting-at, or quote-only;
- optional starting price in TZS;
- active/featured flags;
- SEO metadata;
- request-form availability.

## 8. Content integrity

Until real assets arrive:
- use neutral, clearly labelled development placeholders;
- do not fabricate client names, testimonials, statistics, certifications, timelines, or outcomes;
- portfolio supports `public_named`, `public_anonymous`, and `private/unpublished` confidentiality modes;
- anonymous case studies must remove identifying metadata;
- founder and registration sections remain unpublished until approved content exists.

## 9. Contact expectations

The website may state a normal response objective only after the owner approves operational capacity. Avoid a legal-sounding “guarantee” unless the business has a monitored SLA and exception policy.

## 10. Commercial documents

### Quotes
- draft, sent, accepted, declined, expired, superseded;
- versioned line items;
- TZS default, optional supported currency for international work;
- validity date;
- taxes/discounts only when configured;
- acceptance audit trail.

### Invoices
- draft, issued, partially paid, paid, void, overdue;
- generated from accepted quote or manually;
- immutable issued snapshot except controlled credit/void process.

### Receipts
- generated only after admin records an externally completed/offline payment;
- no payment gateway in v1;
- receipt/legal tax compliance and EFD integration require separate business/legal confirmation.

## 11. Notification policy

Transactional client notifications:
- request received;
- request approved or rejected;
- appointment scheduled/rescheduled/cancelled;
- lead technician assigned;
- work started;
- public message;
- placed on hold/resumed;
- completion submitted where useful;
- completed;
- cancelled;
- reopened;
- quote sent/expiring/accepted;
- invoice issued/overdue;
- receipt issued.

Do not notify on internal notes. Do not send WhatsApp for raw file uploads. Respect channel preferences and provider/template requirements.

## 12. Admin capability boundaries

Only admin may:
- approve/reject/cancel/reopen requests;
- start work;
- make final assignments;
- approve completion;
- issue/void financial documents;
- manage roles/settings;
- publish CMS content.

Staff may prepare drafts and assist communications but restricted actions require admin approval.

## 13. Acceptance philosophy

Every user story must have:
- observable outcome;
- validation rules;
- authorization rule;
- error/empty/loading state;
- audit requirement where relevant;
- automated tests;
- manual verification notes.
