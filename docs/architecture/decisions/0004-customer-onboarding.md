# 4. Customer Onboarding

Date: 2021-05-03

## Status

Proposed

## Context

<!-- The issue motivating this decision, and any context that influences or constrains the decision. -->
*[Customer]*
Action: Customer initates purchase of support contract.
Success: Customer accesses site and login. Log creation.
Failure: Access or account creation not available. Notify admin.

Action: Customer creates or updates account.
Success: Account created or updated. Log update.
Failure: Account creation or update unsuccessful. Notify admin.

Action: Customer adds CC# and selects billing cycle.
Success: CC# and billing cycle added or updated. Log update.
Failure: CC# or billing cycle selection unsuccessful. Notify admin.

Action: Customer receives Invoice.
Success: Invoice generated for customer. Log notification.
Failure: Missing invoice. Notify admin.

Action: Customer pays Invoice.
Success: Invoice payment accepted. Log update. Payment notification sent to customer's preferred inbox.
Failure: Payment incomplete. Notify admin.

Action: Customer receives SysOps Contract.
Success: Contract for product gnerated for customer. Log notification. Notification of contract sent to customer's preferred inbox. Contract sent to customer's acknowledged email.
Failure: Contract incomplete. Notify admin.

*[SysOps]*
Action: Customer profile available to SysOps backend.
Success: Full customer view available: Address, Contact info, Payment, Payment Schedule, Payment expiry, Contract Age, Contract expiry, Product, Product age, Repair/Troubleshoot request history.
Failure: Customer unknown to SysOps. Notify admin.

Action: Capture requirements to supply contracted services.
Success: Capture acceptance criteria (Red, Yel, Grn). 
Failure: Product support requirements unknown to SysOps. Risk sent to reporting real-time queue.

Action: Identify contract with green acceptance criteria.
Success: Log acceptance.
Failure: Acceptance unacknowledged. Soft failure.

Action: Notify manager on yellow or red acceptance criteria. Log notification.
Success: Manager sees contract state and initiates next action.
Failure: Acceptance unacknowledged. Risk sent to reporting real-time queue.

## Decision

<!-- The change that we're proposing or have agreed to implement. -->

## Consequences

<!-- What becomes easier or more difficult to do and any risks introduced by the change that will need to be mitigated. -->
