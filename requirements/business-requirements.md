# Business Requirements — Euronext Market Monitor

Version 0.3 · Owner: J. van Dijk · Status: draft, not signed off

| ID | Priority (MoSCoW) | Sign-off |
|---|---|---|
| BR-01 → BR-05 | Must | Pending — Compliance and DPO comments open |
| BR-06 | Should | Pending |
| BR-07 | Must | Pending — sponsor |

## BR-01: Client monitoring value

The Investor Workspace should help a client monitor instruments of interest between visits without keeping the product open.

- **Rationale:** ~310 "notify me" requests per month; 71% survey interest in price alerts.
- **Measure:** weekly returning users from 21% to 28% within 6 months of general availability.

## BR-02: User control

A client should be able to choose which instruments and conditions to monitor, and to pause, resume, or remove an alert at any time.

- **Rationale:** Discovery interviews — users want to "go quiet" during holidays without losing their setup.

## BR-03: Channel choice

A client should be able to choose among available notification channels (in-app, email, push) and change those preferences later.

- **Note (SK):** Around 12% of accounts have no verified email address today.

## BR-04: Operational supportability

Operations and Client Services should be able to understand the lifecycle of an alert and investigate delivery questions without accessing more personal data than necessary.

- **Measure:** 80% of "I did not receive my alert" tickets answered at first contact (Level 1), without escalation to engineering.

## BR-05: Regulatory and trust posture

Notifications must remain informational. The capability must support applicable market-conduct (MAR, MiFID II), privacy (GDPR, ePrivacy), operational-resilience (DORA), accessibility (EAA), and fair-access controls.

## BR-06: Measurable service

The product team should be able to measure adoption, alert processing, delivery outcomes, failures, and user-facing performance, without exposing personal data in operational reporting.

## BR-07: Phased delivery

R1 should focus on a small set of understandable alert types and approved channels. A closed pilot (Paris + Amsterdam, ~2,000 invited users) must come before general availability. More event types and channels may follow in later releases.

- **Open (CM):** the sponsor asked whether Milan can join the pilot, because Milan has the second-largest retail user base (~18% of MAU).
