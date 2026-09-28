# Functional Requirements

## FR-101: Create an alert rule

An authenticated user can create an alert rule for an eligible instrument by selecting an alert type, entering the required condition, and selecting one or more available notification channels.

## FR-102: Validate an alert rule

The product validates that the instrument, condition, threshold, channel, and user preference are valid before saving the rule. Invalid input must produce an understandable message.

## FR-103: Manage alert rules

A user can view, edit, pause, resume, and delete their alert rules.

## FR-104: Detect an alert event

The alert service evaluates approved market events against active alert rules and records when a rule is triggered.

## FR-105: Deliver a notification

When an active rule is triggered, the service creates a notification for each selected channel and records the delivery outcome.

## FR-106: Avoid repeated notifications

The product applies an agreed repeat-handling rule so that one market event does not create uncontrolled duplicate notifications for the same rule.

## FR-107: Display notification history

The Investor Workspace provides an in-app history of notifications relevant to the user.

## FR-108: Manage channel preferences

A user can view and update channel preferences and any required consent for email or mobile push notifications.

## FR-109: Support investigation

Authorized support users can search alert and delivery records using an agreed set of non-sensitive identifiers and can see an explanation for common failure states.

## FR-110: Provide audit records

The solution records relevant changes to alert rules, preferences, triggering events, and delivery status for the agreed retention period.

## FR-111: Informational presentation

Notification content and the linked workspace view must clearly present market information as informational and must not present an instruction to trade or an investment recommendation.

## FR-112: Coverage configuration

The solution supports an explicit configuration of eligible markets and instrument types so that coverage can be changed through an approved operational process.
