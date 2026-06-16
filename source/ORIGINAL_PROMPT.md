You are a senior full-stack Laravel architect and product engineer.

You are building a complete production-ready platform for:

**BahariDevs Solutions Limited**

A professional technology services company based in Zanzibar and serving Tanzania.

This system consists of THREE integrated layers:

---

# **⚠️ CRITICAL RULE**

You MUST build this system in PHASES.

Each phase must:

* Be fully complete  
* Be testable  
* End with a STOP POINT  
* Require explicit user approval before continuing

DO NOT proceed automatically between phases.

---

# **🧠 SYSTEM ARCHITECTURE OVERVIEW**

The system has three layers:

---

# **1️⃣ PUBLIC WEBSITE LAYER (PRIORITY LAYER)**

This is the **marketing \+ SEO \+ conversion engine** of the company.

It is NOT just informational — it is a lead generation system.

---

## **🎨 BRAND & DESIGN SYSTEM**

### **Visual Identity**

* Primary color: \#021526  
* Accent color: \#72DBF1  
* Secondary color: \#07A0DD  
* Gradient: \#72DBF1 → \#07A0DD

### **Typography**

* Premium self-hosted fonts only (NO Google Fonts)  
* Primary font: Satoshi  
* Alternatives: General Sans, Neue Haas Grotesk  
* Body text size: 20px  
* Large bold headings required  
* Sans-serif system

### **UI Style**

* Dark mode default  
* Light mode toggle available  
* Clean, modern, corporate aesthetic  
* High contrast readability  
* Professional spacing system

### **UX Requirements**

* Smooth scroll animations  
* Fade-in on scroll  
* Hover elevation effects  
* Page transitions  
* Fast loading performance  
* Mobile-first responsive design  
* Accessibility compliance

---

## **🌐 WEBSITE PAGES**

You MUST build the following pages:

### **1\. Home**

* Hero section (strong conversion messaging)  
* Services overview  
* Industries served  
* Why choose us  
* Featured projects  
* Testimonials  
* CTA sections

---

### **2\. About**

* Company story  
* Mission & vision  
* Core values  
* Founder message  
* Trust-building content

---

### **3\. Services**

* Full service catalog:  
  * Systems Development  
  * Web Development  
  * UI/UX Design  
  * Branding  
  * CCTV Installation  
  * Networking  
  * IT Support  
  * Cybersecurity  
  * Server Setup  
  * Cloud & Email Setup  
  * POS Systems  
  * Access Control Systems  
  * Biometric Systems  
  * WiFi Optimization

Each service must include:

* Description  
* Use cases  
* Benefits

---

### **4\. Solutions**

Industry-based solutions:

* Schools  
* Businesses  
* Hotels  
* Clinics  
* Government  
* Retail

---

### **5\. Industries We Serve**

* Education  
* Healthcare  
* Hospitality  
* Corporate  
* Government  
* Retail

---

### **6\. Portfolio**

Case-study format:

Each project includes:

* Title  
* Industry  
* Problem  
* Solution  
* Process  
* Technologies used  
* Timeline  
* Outcome

---

### **7\. Blog**

Categories:

* Technology  
* Security Systems  
* Networking  
* Web & Digital Solutions  
* Maintenance Tips  
* Business Technology

---

### **8\. Contact**

* Contact form  
* Location info  
* Response time guarantee (within 24 hours)  
* Support availability messaging

---

## **🧠 WEBSITE CORE FUNCTION**

The website is NOT static.

It is a conversion system that:

* Builds trust  
* Reduces client uncertainty  
* Generates service requests  
* Feeds into Application Layer

---

# **2️⃣ APPLICATION LAYER (REQUEST \+ BOOKING SYSTEM)**

This is the **operational service system**.

---

## **🧾 CORE FUNCTION**

Handles:

* Service requests  
* Booking scheduling  
* Technician assignment  
* Workflow tracking  
* Client communication

---

## **👤 AUTHENTICATION MODEL**

Single system with roles:

* Admin  
* Staff  
* Technician  
* Client

---

## **🧑 CLIENT SYSTEM**

Clients can:

* Submit requests WITHOUT account (guest allowed)  
* Track request using tracking portal  
* View:  
  * Status  
  * Timeline  
  * Assigned technician name (no contact details)  
  * Communication thread  
  * Completion evidence

---

## **🧾 REQUEST SYSTEM**

A request can include:

* Multiple services  
* File uploads (images, PDFs, screenshots)  
* Priority level:  
  * Low  
  * Normal  
  * High  
  * Emergency

---

## **📌 REQUEST ID FORMAT**

* Prefixed sequential format:  
  Example: BDR-2026-000001

---

## **🔄 WORKFLOW (STRICT STATE MACHINE)**

States:  
Submitted → Approved → Assigned → In Progress → Completed

RULES:

* Only Admin can change status  
* No skipping states allowed  
* Completed requests can be reopened only by Admin

---

## **💬 COMMUNICATION SYSTEM**

Each request includes a threaded messaging system:

Participants:

* Admin (full access)  
* Staff (internal only)  
* Client (external replies)  
* Technician (updates only)

---

## **🔔 NOTIFICATIONS**

Triggered via:

* Email (Mailgun)  
* WhatsApp API

Events:

* Submitted  
* Approved  
* Assigned  
* Completed  
* Cancelled

NO WhatsApp notifications for file uploads.

---

## **🧑‍🔧 TECHNICIAN SYSTEM**

Technicians:

* Have login accounts  
* Only see assigned requests  
* Can:  
  * Add work notes  
  * Upload completion evidence  
* Cannot change status

---

## **👨‍💼 STAFF SYSTEM**

Staff:

* Operational support only  
* View requests  
* Assist admin  
* Cannot assign technicians  
* Cannot change status

---

## **📊 ANALYTICS (ADMIN)**

Dashboard must include:

* Monthly request volume  
* Completed vs pending  
* Technician workload  
* Service distribution

---

# **3️⃣ ADMIN / SYSTEM LAYER**

This is the **internal operations engine**

---

## **🧭 ADMIN DASHBOARD**

Includes:

* Request management  
* Technician assignment (manual only)  
* User management  
* Analytics dashboard  
* Blog management  
* Portfolio management  
* Activity logs  
* System settings

---

## **📁 PORTFOLIO SYSTEM**

Case study format:

* Images  
* Problem  
* Solution  
* Outcome  
* Technologies used

---

## **📎 FILE UPLOAD SYSTEM**

Allowed:

* Images  
* PDFs  
* Screenshots

Rules:

* Validation required  
* Size limits enforced  
* Stored in `/public/uploads`

---

## **🔐 SECURITY REQUIREMENTS**

* CSRF protection mandatory  
* Input validation everywhere  
* Role-based access control  
* Secure file handling  
* Audit logging for request lifecycle

---

# **⚙️ ARCHITECTURE REQUIREMENTS**

* Laravel monolith (modular structure internally)  
* Shared hosting optimized  
* No microservices  
* Service-layer architecture where needed  
* Clean separation of concerns

---

# **🚀 DEVELOPMENT PHASES (CRITICAL)**

You MUST follow this exact order:

---

## **PHASE 1 — PUBLIC WEBSITE SYSTEM**

Build ONLY:

* Full website UI (all pages)  
* Design system implementation  
* Navigation structure  
* SEO-ready structure  
* Static content (no backend logic yet)

STOP AND WAIT FOR APPROVAL

---

## **PHASE 2 — APPLICATION CORE**

Build:

* Authentication system  
* Request creation system  
* File uploads  
* Request storage  
* Request ID generation

STOP

---

## **PHASE 3 — WORKFLOW ENGINE**

Build:

* Strict state machine  
* Admin status control  
* Assignment system  
* Technician visibility rules

STOP

---

## **PHASE 4 — COMMUNICATION SYSTEM**

Build:

* Threaded messaging per request  
* Client tracking portal  
* Status timeline view

STOP

---

## **PHASE 5 — NOTIFICATIONS**

Build:

* Email (Mailgun)  
* WhatsApp integration  
* Event triggers

STOP

---

## **PHASE 6 — ADMIN DASHBOARD**

Build:

* Analytics  
* User management  
* Request management UI  
* Logs system

STOP

---

## **PHASE 7 — POLISH & INTEGRATION**

Build:

* Portfolio system  
* Blog system  
* UI refinement  
* Performance optimization  
* Security hardening

STOP

---

# **📌 FINAL OUTPUT RULES**

* No skipped phases  
* No assumptions outside spec  
* No merging phases  
* Clean Laravel code only  
* Every phase must be independently functional  
* Always end with:  
  "PHASE X COMPLETE — AWAITING APPROVAL"

---

# **🎯 FINAL GOAL**

Deliver a production-ready, scalable platform that:

* Markets BahariDevs professionally  
* Generates leads through the website  
* Handles service requests operationally  
* Manages technicians and workflows  
* Provides admin control and analytics  
* Works efficiently on shared hosting

---

END OF MASTER PROMPT

