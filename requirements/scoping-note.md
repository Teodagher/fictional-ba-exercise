# Scoping Note: Euronext Market Monitor

| | |
|---|---|
| **Purpose** | Discovery input for a proposed investor notification capability |
| **Author** | J. van Dijk (Product Owner), with input from S. Kelly (Client Services) |
| **Audience** | Product, Engineering, Operations, Compliance, DPO office, Market Data Licensing |
| **Version / status** | v0.3 — working draft for analysis. Comments welcome until 30 Sept 2026 |

## 1. Problem statement

Users of the Euronext Investor Workspace must repeatedly come back to the product to check whether instruments in their watchlists have moved or seen unusual activity. Client Services reports that this makes the watchlist weak as an ongoing monitoring tool.

Evidence collected so far:

- **~580 tickets per month** (17% of all Client Services tickets) are tagged "notification". About **310** of them are direct requests for alerts; the rest are complaints about existing email newsletters (not received, duplicates, wrong language).
- In a July 2026 in-app survey (n = 1,214), **71%** of watchlist users said they would "probably" or "definitely" use price alerts; **38%** said they would use volume alerts. Several respondents did not understand what "unusual volume" means.
- 9 of 12 users interviewed in discovery already use a broker app or a third-party website for alerts, then come to Euronext "to check the official data".
- App-store reviews: "no alerts" is the second most frequent complaint (after "no dark mode").

The proposed capability would let a user define alert conditions and receive **informational** notifications through approved channels. The alert should bring the user back to the Workspace, where they can review the underlying market information.

## 2. Expected value

- More frequent and purposeful use of the Investor Workspace (target: +7 points on weekly returning users).
- Better value from watchlists and lower churn of new users.
- Fewer avoidable Client Services contacts (target: –30% "notify me" tickets).
- A controlled, reusable foundation for future investor-channel notifications (for example corporate actions or index events).
- More observable and supportable notification operations than today's ad-hoc email campaigns.

## 3. Questions in scope

- Which alert types are appropriate for R1?
- Which instruments and markets are covered at pilot and at general availability?
- How does a user create, change, pause, and remove an alert?
- What happens during a trading halt, suspension, auction phase, or when an instrument is delisted?
- How are notifications delivered, retried, and expired?
- Are alerts based on **real-time** or **15-minute delayed** data, and what does that mean for licensing and fair access?
- What consent, privacy, market-conduct (MAR, MiFID II), operational-resilience (DORA) and audit controls are needed?
- How will support teams investigate a missing or unexpected notification?

## 4. Constraints and concerns

- Must use approved market-data services only (no direct feed connection).
- Must not provide investment advice or anything that could be read as an investment recommendation under MAR.
- Must not create a latency advantage that could be read as preferential access to market data. The Investor Workspace currently shows **15-minute delayed** prices to non-subscribed users and real-time prices only to users with a real-time data entitlement (~6% of accounts).
- Personal data includes e-mail addresses, device push tokens, alert rules (which can reveal investment interests), notification preferences, and consent records. GDPR applies.
- The email and push providers are third-party ICT providers and must be covered by DORA third-party risk requirements.
- User-facing screens must meet the European Accessibility Act (EN 301 549 / WCAG 2.1 AA).
- Notifications must be available in the six Workspace languages.

## 5. Stakeholder evidence to resolve

- Users want simple rules, but active users may create 20+ rules and several for the same instrument.
- Operations wants a clear explanation when an alert did not arrive — today they cannot answer this for email campaigns.
- Compliance wants informational wording and a visible separation from any order or broker flow.
- DPO wants consent and channel preferences to be explicit and is not convinced alerts are "service messages".
- Engineering needs an agreed definition of an alert event and delivery timing.
- Market Data Licensing needs to confirm whether alerts on real-time data are allowed for users without an entitlement.

## 6. Scope decision needed

The team needs a **traceable R1 scope** and a **list of unresolved decisions** before feature design and delivery estimation can be finalised. The Investment Committee pack is due **6 November 2026** for the **20 November 2026** gate.
