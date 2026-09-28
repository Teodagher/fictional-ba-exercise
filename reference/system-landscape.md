# System Landscape and Information Context

This fictional inventory describes the systems and owners available to the BA team. **It is not an impact assessment.**

| System | Status | Owner (fictional) | Notes |
|---|---|---|---|
| Investor Workspace (web + iOS/Android) | Live | IC — Mobile & Web | Mobile release train every 4 weeks. Web releases weekly. |
| Identity and Access Service | Live | IAM team | Support-role model under review (Q4 2026). |
| Market Data Service | Live | MB — Market Data Eng | Distributes price and volume events. No intraday volume history stored. |
| Alert Evaluation Service | **Proposed** | TBD | New build. |
| Notification Orchestrator | **Proposed** | TBD | New build, or extend the existing marketing email tool? Not decided. |
| Email Provider | Live (3rd party) | Digital Channels | Contract limit 50 msg/s. Delivery receipts: yes. Open tracking: yes (DPO concern). |
| Mobile Push Provider | Live (3rd party) | IC | Token lifecycle managed by the mobile app. |
| In-App Notification Store | **Proposed** | TBD | Retention and deletion to be confirmed. |
| Customer Profile and Consent Service | Live | CRM team | Stores contact details, preferences, consent. Owner of push tokens unclear. |
| Operations Monitoring Platform | Live | TL — SRE | Metrics, logs, alerts, correlation IDs. Role-restricted. |
| Audit and Records Store | Live | Compliance IT | Retention schedules not yet agreed for this product. |
| Support Console | Live | SK — Client Services | Search fields and visibility rules for alerts not defined. |
| Corporate Actions master data | Live | RA — Corporate Actions | 30-min batch. Real-time interface on 2027 roadmap (not committed). |
| Market Data Licensing register | Live | ASG — Licensing & Policy | Holds user real-time entitlements. |

## Descriptions

**Investor Workspace** — Client-facing web and mobile channels. Provides authentication, watchlists, alert setup, notification history, preference screens, and links to instrument pages. Available in EN, FR, NL, IT, PT, NO.

**Identity and Access Service** — Authenticates clients and internal users and provides roles.

**Market Data Service** — Approved internal service distributing price and volume events for covered instruments, with a market timestamp and a service receipt timestamp. Also carries trading phase and halt/suspension status. The alert product must not connect directly to an exchange feed.

**Alert Evaluation Service** — Proposed. Stores active rules, evaluates eligible events, applies the rule lifecycle and repeat handling, and creates notification records.

**Notification Orchestrator** — Proposed. Accepts notification requests, selects the channel provider, handles retries and expiry, and records provider responses.

**Email Provider / Mobile Push Provider** — Third-party ICT providers (in scope of DORA). Capabilities, delivery receipts, and data retention need confirmation.

**In-App Notification Store** — Proposed store behind the notification history.

**Customer Profile and Consent Service** — Contact details, channel preferences, consent records.

**Operations Monitoring Platform** — Service metrics, structured logs, alerts, correlation IDs.

**Audit and Records Store** — Controlled records for changes to settings, rule lifecycle, triggering events, delivery status, and operational actions (including kill-switch use).

**Support Console** — Internal tool used by Client Services to investigate account and notification questions.

## Known interfaces

- Investor Workspace → Identity and Access Service
- Investor Workspace → Customer Profile and Consent Service
- Investor Workspace → Alert Evaluation Service
- Market Data Service → Alert Evaluation Service
- Market Data Licensing register → Alert Evaluation Service (*proposed — only if alerts depend on entitlement*)
- Alert Evaluation Service → Notification Orchestrator
- Notification Orchestrator → Email Provider and Mobile Push Provider
- Notification Orchestrator → In-App Notification Store
- Product services → Operations Monitoring Platform
- Product services and Support Console → Audit and Records Store
- Corporate Actions master data → Investor Workspace event-details service (daily copy, 06:00 CET)
