# Change Request CR-01: Corporate Action Notification Events

| | |
|---|---|
| **Request ID** | CR-01 |
| **Raised by** | Chiara Romano, Investor Services Product Management |
| **Date raised** | 21 Sept 2026 |
| **Sponsor** | Claire Moreau, Head of Retail Services |
| **Requested target** | "R1 if possible, otherwise R1.1" |
| **Priority (requester)** | High |
| **Status** | New — for impact analysis. Not approved for delivery |

## 1. Request

Clients have asked to receive an **informational notification** when a corporate action (for example a dividend, stock split, rights issue, or tender offer) linked to an instrument in their watchlist is **published or materially updated**. Product Management wants to know whether a first version of corporate-action (CA) notifications could be added to the Market Monitor capability.

The notification should send the client to the Investor Workspace for the full event details. It must not tell the client what to do, and must not support elections, instructions, order placement, or any other transaction.

## 2. Requested behaviour to assess

- A client can opt in to CA notifications for eligible instruments or whole watchlists.
- A notification identifies the instrument (name, ISIN) and the CA event type, using approved source information.
- A notification links to the event-details page in the Investor Workspace.
- A material update to an event (for example a changed payment date or dividend amount) may trigger a new notification, following an agreed update rule.
- The client can pause or remove this notification type in the existing preference journey.
- *Requester's wish (not agreed):* a reminder 2 trading days before the ex-date.

## 3. Business reason

- CA information is time-sensitive. Clients depend on manual checks or on separate communications from their broker, which often arrive late.
- Client Services receives **~210 CA-related tickets per month** (deadline questions, "is this dividend still happening?", "why did the price drop on ex-date?").
- In the July 2026 survey, **54%** of watchlist users said they would use dividend notifications.

## 4. Indicative volumes (from Corporate Actions team, not validated)

| Item | Estimate |
|---|---|
| CA events per year on covered instruments (all 7 markets) | ~6,800 |
| Of which cash dividends (DVCA) | ~72% |
| Events corrected or updated at least once | ~15% |
| Events withdrawn or cancelled | ~2% |
| Peak days (dividend season, April–May) | up to 180 events per day |

## 5. Questions for analysis

- Which existing requirements, features, services, data sources, and controls are affected?
- What new behaviour, data, interfaces, roles, or operational processes may be needed?
- Which stakeholders must review the request?
- What are the regulatory, privacy, security, accessibility, reliability, and support implications?
- Can the request fit the R1 boundary (Q2 2027 pilot), or should it be a later phase?
- What information is missing before an estimate or delivery decision can be made?

## 6. Constraints stated by the requester

- No transaction processing or client election workflow.
- No investment advice or recommendation language.
- Only approved Euronext information sources.
- Preserve user control over notification preferences.
- Keep an auditable history of notifications and relevant changes.
