# Fictional Euronext Market Context

This reference is invented for the workshop. It uses the vocabulary and operating shape of a pan-European exchange group, but it does not describe real Euronext systems, products, service levels, clients, or internal processes.

## Operating setting

The fictional Euronext group operates regulated markets across Amsterdam, Brussels, Dublin, Lisbon, Milan, Oslo, and Paris. Its client-facing Investor Workspace presents information about listed instruments from those venues through approved digital channels.

The BA team must consider cross-market differences without designing seven separate products. A single capability may need a common user experience, while instrument eligibility, identifiers, calendars, event timing, language, and source-data quality can vary by venue or market segment.

## Instruments in the case study

- Cash equities listed on one or more fictional Euronext venues.
- Exchange-traded funds available through the Investor Workspace.
- Corporate-action events associated with eligible instruments.

Derivatives, bonds, and non-Euronext instruments are outside the initial product boundary unless a source document explicitly changes that boundary.

## Exchange-operator considerations

- Market information must be presented as information, not investment advice.
- Event timestamps and source timestamps should remain distinguishable where they affect user understanding or operational investigation.
- Coverage and eligibility should be explicit rather than inferred from a user's watchlist alone.
- Access must be fair and non-discriminatory; the notification capability must not become a trading or execution advantage.
- Operational records should support investigation across product, data, channel, compliance, privacy, and support teams.
- Terminology should be consistent across client-facing channels and internal support views.

## Fictional data vocabulary

The case study may use an instrument identifier, ticker, market code, event type, publication timestamp, status, and source reference. The exact formats and values are intentionally left for the requirements and source-system analysis rather than supplied as a completed design.