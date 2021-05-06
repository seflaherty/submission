# 3. Customer to SysOps Ticket Closure WorkFlow

Date: 2021-05-03

## Status

Proposed

## Context

<!-- The issue motivating this decision, and any context that influences or constrains the decision. -->
*[SysOps]*
Action: Expert logs repair/troubleshoot is complete. Trouble ticket event sent to reporting real-time queue.
Success: Acceptance criteria (Red, Yel, Grn). Notification sent to customer's preferred inbox. Log notification.
Failure: Cannot confirm state of ticket. Must notify admin.

Action: Send survey on green acceptance criteria.
Success: Notification of survey sent to customer's preferred inbox. Survey sent to customer's acknowledged email.
Failure: Survey not sent or unacknowledged. Soft failure.

Action: Return ticket to manager on yellow or red acceptance criteria. Log notification.
Success: Manager sees ticket state and initiates next action.
Failure: Ticket goes to dead letter queue. Must notify admin.

*[Customer]*
Action: Customer returns survey to system. Log survey return.
Success: Survey accepted for customer satisfaction analysis.
Failure: Survey data not available.

Action: Customer does not return survey to system.
Success: One-time prompt for customer satisfaction survey sent to customer's acknowledged email. Log notification.
Failure: No response. Survey data not available.


## Decision

<!-- The change that we're proposing or have agreed to implement. -->


## Consequences

<!-- What becomes easier or more difficult to do and any risks introduced by the change that will need to be mitigated. -->
