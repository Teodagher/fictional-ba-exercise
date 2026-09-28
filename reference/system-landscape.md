# System Landscape and Information Context

This fictional inventory describes the systems and responsibilities available to the BA team. It is not an impact assessment.

## Investor Workspace

Client-facing web and mobile channels. Provides authentication, watchlists, alert setup, notification history, preference screens, and links back to market information.

## Identity and Access Service

Authenticates users and provides roles for client-facing and internal support access. The exact support-role model is under review.

## Market Data Service

Approved internal service that distributes price and volume events for covered instruments. Events contain market timestamps and service receipt timestamps. The alert product must not connect directly to an exchange feed.

## Alert Evaluation Service

Proposed service that stores active alert rules, evaluates eligible events, applies rule lifecycle and repeat-handling logic, and creates notification records.

## Notification Orchestrator

Proposed internal service that accepts notification requests, selects the requested channel provider, performs retry handling, and records provider responses.

## Email Provider

Approved channel provider for email delivery. Provider capabilities, delivery receipts, and retention behavior need confirmation.

## Mobile Push Provider

Approved channel provider for mobile push delivery. Device registration and token lifecycle are managed through the mobile platform integration.

## In-App Notification Store

Internal store used to provide notification history in the Investor Workspace. Retention and deletion behavior need confirmation.

## Customer Profile and Consent Service

Stores contact details, channel preferences, and consent records used by client-facing services. The ownership boundary for device identifiers needs confirmation.

## Operations Monitoring Platform

Collects service metrics, structured logs, alerts, and correlation identifiers. Access is restricted by role.

## Audit and Records Store

Stores controlled records for changes to user settings, rule lifecycle, triggering events, delivery status, and operational actions. Retention schedules are not yet agreed.

## Support Console

Internal interface used by Client Services to investigate account and notification questions. Its search fields and visibility rules are not yet finalized.

## Known interfaces

- Investor Workspace to Identity and Access Service
- Investor Workspace to Customer Profile and Consent Service
- Investor Workspace to Alert Evaluation Service
- Market Data Service to Alert Evaluation Service
- Alert Evaluation Service to Notification Orchestrator
- Notification Orchestrator to Email Provider and Mobile Push Provider
- Notification Orchestrator to In-App Notification Store
- Product services to Operations Monitoring Platform
- Product services and Support Console to Audit and Records Store
