# Review comments — Compliance and DPO office

Email thread, forwarded to the BA team by J. van Dijk on 16 Sept 2026. Informal, not a formal opinion.

---

**From:** Pieter Janssens (Market Conduct Compliance)
**To:** Joost van Dijk; Rémi Dumont
**Date:** 15 Sept 2026, 18:12
**Subject:** RE: Market Monitor — notes 8/9 + comments

Joost, Rémi,

A few corrections and comments on the notes:

1. Section 5 — to be precise, I did not say mass alerts *are* a MAR issue. I said we need to assess whether automated alerts on small caps with low liquidity could contribute to disorderly trading. I suggest excluding instruments with an average daily turnover below €100k from volume alerts in R1. Happy to discuss.
2. Wording: no "surge", "soar", "crash", "opportunity", or emojis. Neutral template only, e.g. *"[Instrument] (ISIN) traded at €[price] at [time, zone], crossing your level of €[threshold]. Delayed data / Real-time data. This is information only and not investment advice."*
3. All 6 language versions need sign-off by the local compliance contacts in each market. Allow **3 weeks** for this.
4. Record-keeping: my 5-year comment refers to the audit trail (what was sent to whom, when, with what content). I don't need 5 years of technical retry logs.
5. I need the kill switch (per instrument and global) documented as an operational procedure, with who can use it and how it is logged.
6. Fair access: I support Anne-Sophie's position. Alerts must not give users without entitlement earlier information than the delayed public display.

Regards,
Pieter

---

**From:** Ingrid Solberg (DPO)
**To:** Joost van Dijk; Rémi Dumont; Pieter Janssens
**Date:** 15 Sept 2026, 21:47
**Subject:** RE: RE: Market Monitor — notes 8/9 + comments

Hi all,

Thanks Pieter — with your point 4, I think we can agree: 5 years for the audit record, **13 months** for operational delivery logs, **90 days** for the in-app history visible to the user. To be confirmed in the retention schedule.

My points:

- I need a personal data inventory before the pilot: email, push token, device model/OS, alert rules, thresholds, consent records, delivery logs, IP addresses (if logged). For each: purpose, legal basis, retention, who has access.
- Legal basis: I can accept "contract / service requested by the user" for alerts the user configured. The **daily digest is a different story** — if it includes anything the user did not explicitly ask for, it is marketing and needs opt-in.
- Push tokens: in our EU context I treat them as personal data. Full stop. 🙂
- Support search by email address: I can accept a **masked** search (agent types the full email, system shows only j***@***.com and the account ID) if access is logged. Not free search.
- Deletion: when a user closes their account, alert rules and preferences must be deleted within 30 days. The audit record is kept under a legal-obligation basis.
- DPIA: this is probably needed (profiling of investment interests at scale). Please plan **4–6 weeks**.

Ingrid

---

**From:** Joost van Dijk
**Date:** 16 Sept 2026, 08:05

Thanks both. Rémi, can you please include all of this in the scope and the open decisions list. The 3 weeks of translations + 4–6 weeks of DPIA worry me for the Q2 pilot.
