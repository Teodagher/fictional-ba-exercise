# Fictional Euronext Market Context

This reference is invented for the workshop. It uses public vocabulary and the general operating shape of a pan-European exchange group, but it does **not** describe real Euronext systems, products, service levels, clients, or internal processes. Figures are fictional.

## 1. Operating setting

The fictional group operates seven regulated markets. Its client-facing **Investor Workspace** shows information on instruments listed on those venues.

| Venue | MIC | Local time vs CET | Share of Workspace MAU (fictional) | Covered instruments (est.) |
|---|---|---|---|---|
| Paris | XPAR | same | 34% | ~780 |
| Amsterdam | XAMS | same | 19% | ~570 |
| Milan | MTAA | same | 18% | ~750 |
| Brussels | XBRU | same | 9% | ~240 |
| Oslo | XOSL | same | 8% | ~380 |
| Lisbon | XLIS | –1h | 6% | ~70 |
| Dublin | XMSM | –1h | 6% | ~110 |
| **Total** | | | | **~2,900** (incl. ~1,100 ETFs listed across venues) |

The BA team must consider cross-market differences **without designing seven separate products**. One capability should have a common user experience, while eligibility, identifiers, calendars, holidays, event timing, language, and source-data quality can differ by venue.

## 2. Trading day (cash markets, CET)

| Phase | Time |
|---|---|
| Pre-opening (orders collected, no trades) | 07:15 – 09:00 |
| Opening auction | 09:00 |
| Continuous trading | 09:00 – 17:30 |
| Closing auction | 17:30 – 17:35 |
| Trading at last | 17:35 – 17:40 |

Trading can be interrupted by a **reservation** (automatic halt when price leaves its collar) or a **suspension**. Markets are closed on the common trading calendar holidays, and some venues have extra local holidays.

## 3. Instruments in the case study

- Cash equities listed on one or more Euronext regulated markets.
- ETFs available through the Investor Workspace.
- Corporate-action events linked to eligible instruments (CR-01 only).

Derivatives, bonds, warrants, certificates, Euronext Growth / Access segments, and non-Euronext instruments are outside the R1 boundary, unless a source document explicitly changes that.

## 4. Market data in the Workspace

- Non-subscribed users see prices **delayed by 15 minutes** (free, in line with MiFID II).
- About **6% of accounts** have a **real-time entitlement** through a paid data subscription.
- Data licences are managed by the Market Data Licensing & Policy team. Any new use of real-time data (including triggering alerts) must be checked with them.

## 5. Exchange-operator considerations

- Market information is presented as information, not investment advice (MAR, MiFID II).
- Market (source) timestamps and processing timestamps are kept separate.
- Coverage and eligibility are explicit — not inferred from a user's watchlist.
- Access is fair and non-discriminatory. The notification capability must not become a trading or execution advantage.
- Operational records support investigation across product, data, channel, compliance, privacy, and support teams.
- Terminology is consistent across client channels and internal support tools, in all six languages.
- Third-party ICT providers are managed under DORA.

## 6. Data vocabulary

The case study uses: ISIN, MIC, ticker (mnemonic), instrument name, trading phase, last traded price, traded volume, currency (EUR, NOK), market timestamp (UTC), processing timestamp (UTC), event type, status, and source reference. Exact formats are left for the requirements and source-system analysis.
