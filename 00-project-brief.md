# Euronext Market Monitor

This fictional project concerns a new capability for Euronext investor channels. It is training material for a Business Analyst workshop. It is not an Euronext product proposal and is not affiliated with, endorsed by, or representative of any real internal Euronext system. All names, dates, figures, systems, and requirements are invented.

## Business context

Retail and professional investors use the Euronext Investor Workspace to follow listed instruments, review market information, and maintain personal watchlists. Feedback from client services indicates that users want more timely and relevant notifications without needing to monitor the workspace continuously.

The Product team is exploring a controlled notification capability for selected cash equities and exchange-traded funds listed on Euronext markets. The capability must be useful to clients while remaining informational, reliable, auditable, and consistent with market infrastructure obligations.

## Product outcome

The product should help a user notice a relevant market event and return to the Investor Workspace to investigate it. It must not place orders, recommend investments, or create preferential access to market data.

## Initial goals

- Increase recurring use of the Investor Workspace.
- Make watchlists more useful between visits.
- Give users control over which notifications they receive and where.
- Provide clear evidence of consent, delivery, and operational handling.
- Support a phased release with measurable service quality.

## Initial boundaries

In scope for the first release:

- Alerts based on an instrument price crossing a user-defined threshold.
- Alerts based on an unusual increase in traded volume.
- Delivery through in-app inbox, email, and mobile push notification.
- Cash equities and exchange-traded funds available through the Investor Workspace.
- User-managed alert rules and notification preferences.

Out of scope for the first release:

- Order placement or automated trading.
- Investment advice, recommendations, or portfolio management.
- Derivatives, bonds, and instruments outside the agreed coverage.
- Custom technical indicators such as moving averages or RSI.
- SMS delivery.

## Stakeholders

- Executive sponsor: Head of Retail Services
- Product owner: Investor Workspace Product Owner
- Market data lead: Market Data Engineering Lead
- Digital channels lead: Mobile and Web Product Lead
- Operations lead: Client Services and Operations Manager
- Compliance lead: Market Conduct Compliance Officer
- Privacy lead: Data Protection Officer
- Reliability lead: Site Reliability Engineering Lead

## Planning assumptions

- The product consumes data from existing approved market-data services.
- The first release is planned for a fictional planning year and has not yet received a committed production date.
- The requirements in this repository are discovery material, not an approved delivery baseline.
- The fictional operating context is a pan-European exchange group with venues and clients across Amsterdam, Brussels, Dublin, Lisbon, Milan, Oslo, and Paris.
