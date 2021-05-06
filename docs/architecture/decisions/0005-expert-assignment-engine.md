# 5. Expert Assignment Engine

Date: 2021-05-04

## Status

Proposed

## Context

<!-- The issue motivating this decision, and any context that influences or constrains the decision. -->
The legacy system supporting customer-facing technology experts (the "SysOps Squad") has negatively impacted the business by assigning the incorrect expert consultant to a customer location without the expertise necessary to satisfactorily address the problem, or a larger system failue where useful information is not surfaced in time to successfully answer the customer trouble ticket. What is the appropriate solution for addressing the issue with dispatch of an incorrect expert for the trouble ticket.

## Decision Drivers

*[Expert Assignment Engine]*

* Must assess and rank experts with expertise in the product and cross-sectional expertise in the product-domain from the current pool.
	* Degree of match and appropriate-ness for situation is affected by human factors.
* Must assess the availability of the experts in the current pool.
	* Experts are weighted by the system.
* Must assess the current location and service area of the available experts.
	* Experts are weighted by the system.
* Must calculate the best match at the moment and send a notification to the expert via text message.
	* If the expert is non-responsive within a set amount of time, the Expert Assignment Engine starts the entire process over with a time-limited counterweight on the selected expert. 

## Considered Options

*[Refactor]*

* High chance that a refactor will not successfully reduce the problem areas of the existing system.
* High chance that a refactor will introduce new problem areas into the existing system.
* Slow phasing-in of a refactored system will likely increase confusion in the notifications and responses for both customer and SysOps Squad groups.
* Hard-switch over to a refactored system will likely subject SysOps Squad to old pain-points "with a new coat of paint" and new pain points. It may not be possible to unwind the switch over without medium-to-large opportunity cost. 

*[Replacement]*

* AWS Messaging Services
	* Simple Queue Service (SQS)
		* Serverless: High scale and low cost.
		* Durable. Supports Dead Letter Queues and re-delivery.
	* Simple Notification Service (SNS)
		* Supports delivery to multiple consumers.
			* Does not support delivery guarantees.
		* Supports mobile push notifications and SMS text messages.
		
	
* AWS Event Queue Management


<!-- https://ndcworkshops.com/slot/converting-a-monolithic-app 
1. Strategies for getting started
1. Defining domains when working within a monolithic system
1. Evaluating current unit and integration tests for ability to support refactoring efforts
1. Implementing micro-services over a monolothic back-end
1. Converting historical-data access patterns to CQRS
1. Splitting, segmenting, and changing the business layer to stay within the domain
1. Communicating between domains with events and messaging
1. Dev-Ops considerations in a DDD world
-->

## Decision

<!-- The change that we're proposing or have agreed to implement. -->
TBD

## Consequences

<!-- What becomes easier or more difficult to do and any risks introduced by the change that will need to be mitigated. -->
TBD


## Resources
* [Refactor vs Replacement: A Journey](https://billthevestguy.com/2020/12/22/refactor-vs-replacement-a-journey/)
	* Includes references from doi.org
