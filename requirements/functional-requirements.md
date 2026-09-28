# Functional Requirements — Euronext Market Monitor

Version 0.3 · Owner: J. van Dijk · Status: draft

> Comments in *italics* were added during review and have not been resolved yet.

## FR-101: Create an alert rule

An authenticated user can create an alert rule for an eligible instrument (identified by ISIN and MIC) by choosing an alert type, entering the required condition, and selecting one or more available notification channels.

- Proposed limit: **max 50 active rules per user**, **max 5 rules per instrument**.
- *IC: can we pre-fill from the watchlist? Most users will start from there.*

## FR-102: Validate an alert rule

Before saving, the product checks that the instrument, condition, threshold, channel, and user preference are valid. Invalid input shows a clear message in the user's language.

- Example checks: threshold must be > 0; threshold within ±50% of last price (to prevent typos such as 1,000 instead of 10.00); channel must have valid consent.
- *MB: the ±50% rule breaks for penny stocks and for instruments after a reverse split.*

## FR-103: Manage alert rules

A user can view, edit, pause, resume, and delete their alert rules. They can pause all rules at once ("holiday mode") and set an optional end date for the pause.

## FR-104: Detect an alert event

The Alert Evaluation Service evaluates approved market events against active rules and records when a rule is triggered.

- Price alerts use the **last traded price** during continuous trading (09:00–17:30 CET).
- *Open: what about the opening auction, the closing auction (17:30–17:35) and the trading-at-last phase (17:35–17:40)? What about a trading halt ("reservation") or a suspension?*

## FR-105: Deliver a notification

When an active rule is triggered, the service creates one notification per selected channel and records the delivery outcome for each channel.

## FR-106: Avoid repeated notifications

The product applies an agreed repeat-handling rule so that one market event does not generate uncontrolled duplicates for the same rule.

- Option A (Product): re-arm the rule once price moves back 1% the other side of the threshold.
- Option B (Client Services): max 1 notification per rule per trading day.
- Option C (Mobile): daily digest option at 18:00 local time.
- *Not decided.*

## FR-107: Display notification history

The Investor Workspace shows an in-app history of notifications relevant to the user, for **90 days** (proposed). Each entry shows the instrument, condition, event time, and a link to the instrument page.

## FR-108: Manage channel preferences

A user can view and update channel preferences and any required consent for email or mobile push. Changes apply to new notifications within 1 minute.

## FR-109: Support investigation

Authorised support users can search alert and delivery records by an agreed set of non-sensitive identifiers (for example Workspace account ID, rule ID, notification ID, date range) and see a plain-language explanation for common failure states.

- *SK: agents are used to searching by email address. DPO says no.*

## FR-110: Provide audit records

The solution records changes to alert rules, preferences and consent, triggering events, and delivery status for the agreed retention period (**not agreed — 13 months vs 5 years**, see review comments).

## FR-111: Informational presentation

Notification content and the linked Workspace view must present market information as informational only. They must not contain an instruction to trade, an investment recommendation, urgency language ("Act now!"), or a ranking.

- Every notification must say whether the price is **real-time** or **delayed**.

## FR-112: Coverage configuration

The solution supports an explicit configuration of eligible markets (by MIC) and instrument types, so coverage can be changed through an approved operational process with four-eyes approval.

- Pilot coverage: XPAR + XAMS cash equities and ETFs (~1,350 instruments).
- General availability: all seven regulated markets (~2,900 instruments, estimate from Market Data).
