# Feature Discovery Input — raw material

Collected by R. Dumont (BA), July–Sept 2026. This is raw input for the feature documentation. **It is not a feature specification.**

## 1. Interview extracts (12 users, July 2026)

> "I want to know when something I follow crosses a level I care about. That's it. I don't want a 'market update'." — P1, retail, Lyon

> "I need to pause alerts when I'm on holiday without deleting all my setup. Last time with my bank app I lost 30 alerts." — P2, active investor, Rotterdam

> "If I get an email and a push, I need to understand whether it's the same event or two different ones." — P2, active investor, Milan

> "The time on the alert must be the market time. If it says 14:32, I want to know it's 14:32 in Paris, not on my phone in Lisbon." — P3, professional, Lisbon

> "Is the price in the alert live or delayed? On your website it's delayed, right?" — P1, retail, Brussels

> "I set an alert at €50, the stock opened at €47 after results. Did I miss the alert or did it never trigger?" — P2, Oslo

> "Please don't put 'buy' or 'sell' buttons. I have a broker for that. I come here for the official data." — P3, Amsterdam

## 2. Client Services extract (tickets tagged "notification", Jan–Aug 2026)

| Category | Tickets / month (avg) |
|---|---|
| "Can you notify me when…" (feature request) | 312 |
| "I didn't receive the email" (existing newsletters) | 148 |
| "I received it twice" | 41 |
| "Unsubscribe doesn't work" | 36 |
| "Wrong language" | 22 |
| Other | 21 |
| **Total** | **~580** |

Average time to answer a "didn't receive" ticket today: **4.1 days** (needs an IT escalation in 85% of cases).

## 3. Capability themes noted so far (not validated, not complete)

- Set up and manage an alert rule
- Evaluate price and volume conditions
- Deliver through the selected channels
- Notification history
- Consent and channel preferences
- Support investigation
- Service health monitoring and audit trail
- *(anything missing? kill switch? coverage admin? holiday mode?)*

## 4. Questions the feature documentation must answer

- What is the smallest useful R1 slice for the Q2 2027 pilot?
- Which rules and states must be visible to the user?
- What happens when an instrument becomes ineligible, is halted, suspended, or delisted?
- What is the expected behaviour when a channel provider is unavailable?
- What evidence is needed for Compliance, DPO, and Client Services?
- Which acceptance criteria can be tested from the stated requirements — and which requirements are too vague to test?
