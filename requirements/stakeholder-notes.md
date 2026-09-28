# Stakeholder Meeting Notes: Monitor Notifications Discovery

**Meeting type:** Discovery workshop

**Status:** Unapproved working notes

**Participants:** Product Owner, Market Data Engineering Lead, Mobile and Web Product Lead, Client Services and Operations Manager, Market Conduct Compliance Officer, Data Protection Officer, Site Reliability Engineering Lead

## Discussion notes

- Product sees price threshold and unusual-volume alerts as understandable starting points. The definition of unusual volume needs a business and data decision.
- Mobile and Web wants alert setup to be short and consistent across web and mobile. The team does not want a notification journey to become an order journey.
- Market Data Engineering says the alert service should consume the approved internal market-data stream. The source event timestamp and processing timestamp should remain distinguishable.
- Operations needs to know whether a rule was inactive, an event was not eligible, a channel was not consented, a provider failed, or a message was delivered.
- Compliance requested that wording avoid advice, urgency, ranking, or language that could be interpreted as a recommendation. They also raised fair-access and market-abuse considerations for review.
- Privacy requested an explicit inventory of personal data, channel consent, retention, deletion, and access controls. The group has not agreed whether device-level push identifiers should be treated as personal data in all operating contexts.
- Reliability wants a single correlation identifier across rule evaluation, notification creation, provider hand-off, retry, and final status.
- Client Services asked whether users could receive several notifications for the same instrument and whether there should be a limit or digest option.

## Points not resolved in the meeting

- Exact unusual-volume calculation and required data history.
- Repeat and duplicate handling across channels.
- Service-level targets and the operating window.
- Retention period for alert and delivery records.
- Which support roles may view delivery details.
- Whether additional channels should be considered after the first release.
- Which markets and instrument categories are eligible at launch.

## Follow-up evidence

The Product Owner will provide a proposed first-release scope. Compliance and Privacy will provide review comments before the scope is treated as a baseline. Engineering and Operations will propose service and investigation measures.
