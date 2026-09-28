# Non-Functional Requirements

## NFR-201: Timeliness

The product team must define and measure the time from an eligible market event being received by the alert service to the notification request being handed to the selected channel provider.

## NFR-202: Availability

Alert processing and notification history should meet an agreed availability target during the operating window. The target and exclusions remain to be confirmed.

## NFR-203: Resilience

A temporary channel-provider or internal service failure must not silently lose an eligible notification. Retry, expiry, and dead-letter handling must be defined.

## NFR-204: Observability

The service must expose operational metrics, structured logs, correlation identifiers, and alerts for processing or delivery failures without logging unnecessary personal data.

## NFR-205: Security

Only authorized users and services may view or modify alert rules, contact details, preferences, delivery records, and operational configuration.

## NFR-206: Privacy

The solution must support data minimization, purpose limitation, consent where required, subject-rights handling, retention, and deletion processes for personal data.

## NFR-207: Accessibility

User-facing alert setup, preference management, and notification history should meet the applicable accessibility standard used by the Investor Workspace.

## NFR-208: Scalability

The design must accommodate growth in active users, alert rules, market events, and notifications. Capacity assumptions and performance test volumes are not yet agreed.

## NFR-209: Traceability

A support or audit investigation should be able to connect an alert rule, triggering event, notification attempt, and final status through a controlled correlation identifier.
