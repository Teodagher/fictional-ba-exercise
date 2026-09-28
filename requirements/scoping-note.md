# Scoping Note: Euronext Market Monitor

**Purpose:** Discovery input for a proposed investor notification capability

**Audience:** Product, Engineering, Operations, Compliance, and Data Protection stakeholders

**Status:** Working draft for analysis

## Problem statement

Users of the Euronext Investor Workspace must repeatedly return to the product to check whether instruments in their watchlists have moved or experienced unusual activity. Client Services reports that this makes the watchlist less useful as an ongoing monitoring tool.

The proposed capability would allow a user to define alert conditions and receive informational notifications through approved channels. The alert should bring the user back to the workspace, where the user can review the underlying market information.

## Expected value

- More frequent and purposeful use of the Investor Workspace.
- Better value from watchlists.
- A controlled foundation for future investor-channel notifications.
- More observable and supportable notification operations.

## Questions in scope

- Which alert types are appropriate for the first release?
- Which instruments and markets are covered?
- How does a user create, change, pause, and remove an alert?
- How are notifications delivered and retried?
- What consent, privacy, market-conduct, and audit controls are needed?
- How will support teams investigate a missing or unexpected notification?

## Constraints and concerns

The capability must use approved market-data services, must not provide investment advice, and must not create a latency advantage that could be interpreted as preferential access. Personal data includes contact details, device identifiers, alert rules, and notification preferences. The design must support appropriate retention, access control, auditability, and deletion handling.

## Stakeholder evidence to resolve

- Users want simple rules but may create several rules for the same instrument.
- Operations wants a clear explanation when an alert did not arrive.
- Compliance wants informational wording and a visible separation from order workflows.
- Privacy stakeholders want consent and channel preferences to be explicit.
- Engineering needs an agreed definition of an alert event and delivery timing.

## Scope decision needed

The team needs a traceable first-release scope and a list of unresolved decisions before feature design and delivery estimation can be finalized.
