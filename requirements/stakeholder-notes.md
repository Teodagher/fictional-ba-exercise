# Discovery Workshop — Market Monitor notifications

**Date:** Tue 8 Sept 2026, 14:00–16:00 CET (Paris office + Teams)
**Notes by:** R. Dumont (BA)
**Status:** unapproved working notes — sent to participants 9/9, corrections received from PJ and IS (see review comments file)

**Present:** JvD (PO), MB (Market Data Eng), IC (Mobile & Web), SK (Client Services & Ops), PJ (Compliance), IS (DPO, joined 14:40), TL (SRE)
**Apologies:** ASG (Market Data Licensing) — sent comments by email, read out by JvD

---

### 1. Alert types for R1

- JvD: price threshold + unusual volume. "Price is the must-have, volume is the differentiator — nobody else has official volume data."
- MB: fine for price. For volume, we need the definition first. Current idea: *volume in a 30-min window > 3× the 20-day average for the same window, minimum 10,000 shares*. That means storing 20 days of intraday history per instrument — we don't have that today. Estimated extra 6–8 weeks.
- IC: users in the survey didn't understand "unusual volume". Worried about support calls.
- SK agrees with IC. JvD: "then we explain it better, we don't drop it". **No agreement.**

### 2. Journey / channels

- IC: setup must be max 3 steps and identical on web and app. Strong no to any "Trade now" button or link to broker partners in the notification. PJ agreed strongly.
- IC: push opt-in rate on our app is only ~41% (iOS lower, ~34%). So many users will only have in-app + email.
- SK: ~12% of accounts have no verified email.

### 3. Market data / timing

- MB: service must consume the internal Market Data Service stream, not the raw feed. Source (market) timestamp and our processing timestamp must stay separate.
- ASG (by email, read by JvD): *"Alerts on real-time prices to users with no real-time entitlement = a licensing problem and potentially a fair-access problem. Either alert on delayed data (15 min) or restrict to entitled users."*
- TL: "so our 5-second target is pointless for 94% of users?" JvD: "we'll need to decide." → **Open, escalate to CM.**
- MB raised: what happens in auctions, halts ("reservations"), suspensions? Price can jump at the reopening auction and trigger lots of alerts at once.

### 4. Operations

- SK needs to tell a client which of these happened: rule inactive / paused, event not eligible, channel not consented, provider failed, message delivered-but-not-opened. Today, for email campaigns, "we have nothing, we escalate every case to IT, it takes 4 days on average".
- SK wants L1 agents to search by email address. IS (joined late): no — use account ID. SK: "clients don't know their account ID." → Open.

### 5. Compliance

- PJ: no advice, no urgency, no ranking ("Top 5 movers" is out). Standard disclaimer in every notification. Wording templates for all 6 languages must be reviewed by Compliance before go-live.
- PJ: MAR — mass volume alerts could, in theory, amplify price moves in small caps. Wants a view on this before the pilot. Also asked for a "kill switch" to stop all alerts on an instrument within 5 minutes.
- PJ: MiFID II record-keeping → keep notification records **5 years**.

### 6. Privacy

- IS: full personal data inventory needed. Alert rules reveal investment interest → personal data. Push tokens → personal data in her view; MB/IC disagree ("it's a device ID, not a person").
- IS: is an alert a service message or marketing? If marketing → ePrivacy opt-in for email and push. JvD: "it's clearly a service". IS: "the user asked for it, maybe — but the digest idea looks like marketing".
- IS: 5-year retention is too long for delivery logs; proposes 13 months. PJ: "not negotiable for the audit record". → Open, needs a split between audit and operational records?

### 7. Reliability

- TL: one correlation ID across rule evaluation → notification creation → provider hand-off → retries → final status. Non-negotiable for SRE.
- TL: email provider limit is 50 msg/s. At 09:00 open with 150k rules we could hit it.

### 8. Duplicates

- SK: clients complain today about getting the same info by email + push. Asked for a limit per day or a digest.
- JvD: prefers "re-arm after 1% move back". IC prefers a daily digest option. Not decided.

---

### Not resolved

1. Unusual-volume definition and required data history (MB, +6–8 weeks?)
2. Real-time vs delayed data for alerts — licensing and fair access (ASG / CM)
3. Repeat and duplicate handling across channels (JvD / SK / IC)
4. Service-level targets and operating window (TL)
5. Retention: 13 months vs 5 years (IS / PJ)
6. Support search fields and which roles see delivery details (SK / IS)
7. Pilot markets — Paris + Amsterdam only, or add Milan? (CM)
8. Behaviour during auctions, halts, suspensions, delisting (MB)
9. Are push tokens personal data in all contexts? (IS)

### Actions

| # | Action | Owner | Due |
|---|---|---|---|
| A1 | Proposed R1 scope v1 | JvD | 22/09 |
| A2 | Volume definition + data history estimate | MB | 18/09 |
| A3 | Written position on real-time vs delayed | ASG | 18/09 |
| A4 | Compliance review comments | PJ | 15/09 ✅ |
| A5 | Privacy review comments + data inventory template | IS | 15/09 ✅ |
| A6 | SLO proposal + peak load test volumes | TL | 25/09 |
| A7 | Top 10 support scenarios "alert not received" | SK | 25/09 |

Next meeting: 29/09, 10:00 CET.
