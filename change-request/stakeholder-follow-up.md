# CR-01 — follow-up call notes

**Date:** Thu 24 Sept 2026, 11:00–11:45 CET (Teams)
**Notes by:** R. Dumont (BA) — quick notes, not reviewed
**Present:** Chiara Romano (CR, Investor Services PM), SK (Client Services), JvD (PO), Rui Almeida (RA, Corporate Actions), IC (Mobile & Web) for the last 15 min

---

- CR: wants the change assessed **before** committing to a date. Sponsor (CM) would "love to announce dividends alerts at the pilot".
- JvD: honestly worried. R1 is already tight (DPIA, translations, volume definition). Doesn't want CR-01 to push the pilot.
- SK: clients ask about deadlines, updates, and "is this event still on?". Does **not** want the notification to become a second event-management system: "one line + link, full stop".
- RA: Corporate Actions owns the authoritative content. But: no real-time feed today, only a 30-min batch. "If you promise real-time CA alerts, you can't deliver."
- RA: about 15% of events get corrected. Some corrections are just typos in the free text — "you don't want to notify 20,000 people for a typo".
- CR: proposes one notification at first publication + one per **material change**. Nobody could agree on what "material" means. RA suggests: amount, currency, ex-date, record date, payment date, status → material. Free text → not material. CR: "what about the election deadline?" → open.
- SK: how will Operations tell a new event from an update, and how do we investigate "I never got the update"?
- JvD: Compliance (PJ) wants to review all CA wording and templates — "3 weeks again, in 6 languages".
- JvD: DPO (IS) will ask: existing alert consent, a separate CA preference, or both? Not discussed with her yet.
- IC (joined late): today's notification history screen assumes one price + one time + one link. CA needs several dates and a status. "That's a redesign of the card, not a tweak." Estimate: 3–4 weeks of design + build.
- IC: also, the mobile app release train is every 4 weeks — the next slots are 12 Jan and 9 Feb 2027.
- Nobody from Engineering (MB) present. Unknown whether the Market Data event pipeline can carry CA events at all, or whether it needs a separate connector.
- CR: "Can we at least do dividends only (DVCA) for Paris?" → noted as an option.

### Actions

| # | Action | Owner | Due |
|---|---|---|---|
| B1 | Confirm pipeline suitability for CA events | MB | 02/10 |
| B2 | Draft list of "material" fields | RA | 02/10 |
| B3 | Consent position for CA notifications | IS | 06/10 |
| B4 | Impact analysis + summary deck for sponsor | R. Dumont (BA) | 09/10 |
