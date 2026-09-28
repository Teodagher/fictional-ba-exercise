# Non-Functional Requirements — Euronext Market Monitor

Version 0.2 · Owners: T. Lefèvre (SRE), M. Bellini (Market Data) · Status: draft — several targets are **proposals only**

## NFR-201: Timeliness

The team must define and measure the time from an eligible market event being received by the Alert Evaluation Service to the notification request being handed to the channel provider.

- SRE proposal: **p95 ≤ 5 seconds, p99 ≤ 30 seconds** during continuous trading.
- Market Data Licensing (ASG): if the user has no real-time entitlement, the alert must not be sent **before the 15-minute delay** has passed. *Not yet reflected in the design.*

## NFR-202: Availability

Alert processing and notification history must meet an agreed availability target during the operating window.

- Proposal: **99.5%** monthly, between **07:00 and 19:00 CET** on Euronext trading days (≈ 255 days per year).
- Out of the window: best effort; the in-app history may be read-only.
- Exclusions (planned maintenance, provider outages) to be confirmed.

## NFR-203: Resilience

A temporary failure of a channel provider or internal service must not silently lose an eligible notification.

- Proposal: retry with back-off up to **3 attempts over 10 minutes**. After that the notification is marked *expired* and sent to a dead-letter queue.
- Notifications older than **30 minutes** must not be delivered (the information is out of date).
- DORA: both email and push providers are ICT third-party providers. They must appear in the register of information, and their incidents must follow the ICT incident classification process.

## NFR-204: Observability

The service exposes operational metrics, structured logs, correlation IDs, and alerts for processing or delivery failures. Logs must not contain email addresses, push tokens, or rule thresholds in clear text.

## NFR-205: Security

Only authorised users and services may view or change alert rules, contact details, preferences, delivery records, and operational configuration. Support access uses role-based access and is reviewed every quarter.

## NFR-206: Privacy

The solution supports data minimisation, purpose limitation, consent where required, data-subject rights (access, deletion — answer within **30 days**), retention, and deletion processes under GDPR.

- Alert rules can reveal a person's investment interests. DPO asks to treat them as personal data.

## NFR-207: Accessibility

Alert setup, preference management, and notification history must meet **WCAG 2.1 AA / EN 301 549**, as required by the European Accessibility Act since 28 June 2025.

## NFR-208: Scalability

The design must handle growth in users, rules, market events, and notifications.

Planning volumes (Market Data + Product estimate, not validated):

| Item | Pilot | General availability, year 1 |
|---|---|---|
| Users with active rules | 2,000 | 19,000 – 30,000 |
| Active rules | 8,000 | 90,000 – 150,000 |
| Price/volume events received per trading day | ~9 million | ~22 million |
| Notifications per trading day (average) | ~1,500 | ~25,000 |
| Peak notifications per minute (market open, big news) | ~400 | ~6,000 |

- Email provider contract limit: **50 messages per second** — *TL: this may not be enough at peak.*

## NFR-209: Traceability

A support or audit investigation must be able to connect an alert rule, triggering event, notification attempt, and final status through one controlled correlation ID.

## NFR-210: Localisation

Notifications and screens are available in EN, FR, NL, IT, PT, and NO. Times are shown in the user's local time zone with the zone name (e.g. "14:32 CET", "13:32 IST").
