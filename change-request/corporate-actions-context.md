# Corporate Actions — domain context for CR-01

Prepared with input from Rui Almeida (Corporate Actions team lead, fictional). This describes the information domain. **It does not decide the solution.**

## 1. What a corporate-action record contains

A CA record may include:

- Issuer name and LEI; instrument ISIN; listing market (MIC).
- **Event type**, using ISO 15022 / ISO 20022 codes, for example:
  - DVCA — cash dividend
  - DVSE — stock dividend
  - SPLF — stock split
  - RHTS — rights issue
  - TEND — tender offer
  - MRGR — merger
  - BONU — bonus issue
- Event status: *preliminary (unconfirmed)*, *confirmed*, *replaced*, *cancelled / withdrawn*.
- Announcement timestamp (when the issuer published) and processing timestamp (when our system received it).
- Key dates, where relevant: **announcement date, ex-date, record date, payment date**, election deadline (for voluntary events).
- Structured terms (amount per share, currency, ratio) and free explanatory text — sometimes only in the issuer's local language.
- Source reference and a **version number** (not provided by all sources).

The available fields, update rules, identifier quality, and publication guarantees must be confirmed with the Corporate Actions team.

## 2. Candidate information sources

| Source | Notes |
|---|---|
| Corporate Actions master data service | Authoritative for Euronext-listed events. Batch every 30 min today; a real-time interface is on the roadmap for 2027 (not committed). |
| Investor Workspace event-details service | Displays CA pages today. Takes a daily copy at 06:00 CET. |
| Issuer announcement repository | Original PDFs and press releases. Unstructured. |
| Client Services knowledge base | Explanations for clients. Not a data source. |

The authoritative source and the integration contract have **not** been selected.

## 3. Operational facts raised in discovery

- About 15% of events are corrected at least once; some are corrected **after** the ex-date.
- Corrections can change the amount, the dates, or the currency without changing the event type.
- Some events are replaced (new event ID) rather than updated — the link between old and new is not always explicit.
- Timing differs by market: some issuers publish after market close (after 17:40 CET), others in the morning before 07:00 CET.
- Explanatory text for events in Oslo and Milan is often only in Norwegian or Italian.
- To answer a complaint, the team may need to show **what the client was told at a given point in time** (the version of the event at that time).
- Some terms (for example "scrip dividend", "DRIP", "subscription right") need a controlled glossary and Compliance review.

## 4. Regulatory touch points to consider

- **Shareholder Rights Directive II (SRD II):** applies to intermediaries, not to this informational notification — but Compliance wants the difference to be explicit so clients don't think Euronext is their intermediary.
- **MAR:** CA information is public inside information once published by the issuer. A notification must never go out *before* official publication.
- **GDPR / ePrivacy:** same questions as for price alerts (consent, retention).
