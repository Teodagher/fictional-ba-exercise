# Euronext Market Monitor — Project Brief

> **Training material.** This fictional project was written for a Business Analyst workshop. It is not a Euronext product proposal and is not affiliated with, endorsed by, or representative of any real Euronext system, team, or decision. All names, people, dates, figures, systems, and requirements are invented. Public market vocabulary (ISIN, MIC codes, trading phases, regulations) is used for realism only.

| | |
|---|---|
| **Document owner** | Joost van Dijk (JvD), Product Owner — Investor Workspace |
| **Version** | 0.4 (draft) |
| **Last updated** | 2 September 2026 |
| **Status** | Discovery — not a delivery baseline |
| **Distribution** | Retail Services leadership, Product, Engineering, Operations, Compliance, DPO office |

## 1. Business context

Retail and professional investors use the **Euronext Investor Workspace** (web + iOS/Android app) to follow instruments listed on Euronext venues, read market information, and maintain personal watchlists.

Key figures (Investor Workspace analytics, H1 2026):

| Metric | Value |
|---|---|
| Registered accounts | ~412,000 |
| Monthly active users (MAU) | ~96,500 |
| Share of sessions on mobile | 63% |
| Accounts with at least one watchlist | 58% |
| Average instruments per watchlist | 9.4 (median 6) |
| Users returning ≥ 3 times per week | 21% |
| 90-day churn of new watchlist users | 44% |

Client Services logged **3,420 tickets per month** on average in H1 2026. Around **17%** of them (~580) are tagged "notification": roughly half are requests such as *"Can you notify me when…"*, the rest are problems with today's email newsletters. Competitor broker apps already offer price alerts, and investors increasingly expect the same from the exchange's own channel.

The Product team is exploring a controlled **notification capability** for selected cash equities and exchange-traded funds (ETFs). The capability must be useful to clients while remaining informational, reliable, auditable, and consistent with Euronext's obligations as a market operator.

## 2. Product outcome

The product should help a user **notice a relevant market event and return to the Investor Workspace to investigate it**.

It must **not** place orders, recommend investments, rank instruments, or create preferential access to market data.

## 3. Initial goals and success measures (proposed, not agreed)

| Goal | Proposed KPI | Target after 6 months |
|---|---|---|
| Increase recurring use | Users returning ≥ 3×/week | 21% → 28% |
| Make watchlists more useful | 90-day churn of watchlist users | 44% → 35% |
| Adoption | MAU with ≥ 1 active alert rule | 20% (~19,000 users) |
| Reduce avoidable support contacts | "Notify me" tickets per month | –30% |
| Service quality | Notifications handed to provider within target time | ≥ 99% |
| Trust | Complaints about wrong / duplicate alerts | < 0.1% of notifications |

## 4. Initial boundaries

**In scope for release 1 (R1):**

- Alert when an instrument's last traded price crosses a user-defined threshold (above / below).
- Alert on an unusual increase in traded volume (definition to be agreed — see stakeholder notes).
- Delivery through in-app inbox, email, and mobile push notification.
- Cash equities and ETFs listed on Euronext regulated markets and available in the Investor Workspace.
- User-managed alert rules, pause/resume, and notification preferences.
- Interface languages already supported by the Workspace: EN, FR, NL, IT, PT, NO.

**Out of scope for R1:**

- Order placement, order routing, or any link to a broker execution flow.
- Investment advice, recommendations, "top movers" rankings, or portfolio management.
- Derivatives, bonds, warrants and certificates, Euronext Growth / Access segments, and non-Euronext instruments.
- Custom technical indicators (moving averages, RSI, MACD).
- SMS, WhatsApp, or other messaging channels.

## 5. Stakeholders

| Role | Name (fictional) | Initials |
|---|---|---|
| Executive sponsor — Head of Retail Services | Claire Moreau | CM |
| Product Owner — Investor Workspace | Joost van Dijk | JvD |
| Market Data Engineering Lead | Marco Bellini | MB |
| Mobile and Web Product Lead | Inês Carvalho | IC |
| Client Services and Operations Manager | Siobhán Kelly | SK |
| Market Conduct Compliance Officer | Pieter Janssens | PJ |
| Data Protection Officer (DPO) | Ingrid Solberg | IS |
| Site Reliability Engineering (SRE) Lead | Thomas Lefèvre | TL |
| Market Data Licensing & Policy | Anne-Sophie Girard | ASG |
| Business Analyst | Rémi Dumont | RD |

## 6. Budget, team and timeline (indicative)

- Indicative R1 envelope: **€780k–€920k** (build + first-year run). Not yet approved by the Investment Committee.
- Team: 2 delivery squads (≈ 12 FTE) + shared SRE and QA capacity.
- Target: **closed pilot in Q2 2027** (Paris and Amsterdam instruments, ~2,000 invited users), general availability later in 2027. No committed production date.
- Investment Committee gate: **20 November 2026** — requires a traceable R1 scope, an impact view, and a list of open decisions.

## 7. Planning assumptions

- The product consumes data only from the approved internal **Market Data Service**. No direct connection to exchange feeds.
- The pan-European operating context covers seven regulated markets: Amsterdam (XAMS), Brussels (XBRU), Dublin (XMSM), Lisbon (XLIS), Milan (MTAA), Oslo (XOSL), and Paris (XPAR).
- Dublin and Lisbon run one hour behind CET. All operational timestamps are stored in UTC.
- The requirements in this repository are discovery material, not an approved delivery baseline.
