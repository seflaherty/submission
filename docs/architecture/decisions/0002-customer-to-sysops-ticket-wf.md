# 2. Customer to SysOps Ticket Intake WorkFlow

Date: 2021-05-03

## Status

Proposed

## Context

<!-- The issue motivating this decision, and any context that influences or constrains the decision. -->
Document the expectations and impact of the moment a customer reporting an issue with a product that has a valid SysOps support plan.

*[Customer]*
Action: Perform Login.
Success: Authenticated to site and taken to greeting page.
Failure: Cannot authenticate.

Action: Report problem with product.
Success: Successfully taken-in on site. Email sent to customer's acknowledged inbox.
Failure: Cannot create report or report created by customer cannot verify.

*[SysOps]*
Action: Intake trouble ticket.
Success: Route ticket to on-hand Expert matching.
Failure: Ticket goes to dead letter queue. Must notify admin.

Action: Log Expert-matching.
Success: Expert match completed by system.
Failure: No match completed.  Must notify admin.

Action: Trouble ticket event sent to reporting real-time queue.
Success: Manager sees incoming ticket.
Failure: Ticket unreported/unacknowledged. Soft failure.

Action: Manager confirms ticket event and Expert match. Logged notification.
Success: Capture acceptance criteria (Red, Yel, Grn).
Failure: Expert match proceeds without oversight. No log of notification. Soft failure.

Action: Expert confirms ticket acceptance in system. Trouble ticket event sent to reporting real-time queue.
Success: Customer trouble ticket to Expert match complete. Email sent to customer's acknowledged inbox.. Logged notification.
Failure: Ticket goes to dead letter queue. Must notify admin.


## Decision

<!-- The change that we're proposing or have agreed to implement. -->


## Consequences

<!-- What becomes easier or more difficult to do and any risks introduced by the change that will need to be mitigated. -->
