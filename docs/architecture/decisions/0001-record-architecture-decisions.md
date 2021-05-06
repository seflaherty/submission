# 1. Record architecture decisions

Date: 2021-05-03

## Status

Accepted | Evergreen

## Context

We need to record the architectural decisions made on this project.

### Overview of this project

#### The Sysops Squad

> Penultimate Electronics is a large electronics giant that has numerous retail stores throughout the country. When customers buy computers, TV’s, stereos, and other electronic equipment, they can choose to purchase a support plan. Customer-facing technology experts (the “Sysops Squad”) will then come to the customers residence (or work office) to fix problems with the electronic device.

> Source: Meet the Client!!<br>
> Provided on April 21, 2021 by Neal Ford at Kickoff


#### The Problem
> Things have not been good with the Sysops Squad lately. The current trouble ticket system is a large monolithic application that was developed many years ago. Customers are complaining that consultants are never showing up due to lost tickets, and often times the wrong consultant shows up to fix something they know nothing about. Customers and call-center staff have been complaining that the system is not always available for web-based or call-based problem ticket entry. Change is difficult and risky in this large monolith - whenever a change is made, it takes too long and something else usually breaks. Due to reliability issues, the monolithic system frequently “freezes up” or crashes - they think it’s mostly due a spike in usage and the number of customers using the system. If something isn’t done soon, Penultimate Electronics will be forced to abandon this very lucrative business line and fire all of the experts (including you, the architect).

> Source: Sysops Squad - A Bad Situation…<br>
> Provided on April 21, 2021 by Neal Ford at Kickoff

## Decision Drivers

*[Top-level]*

* The large monolithic application is…
	* Frequently unavailable to both customers and call-center staff.
	* Difficult to change. Changes risk regressions elsewhere in the application.
	* "Freezing up" or crashing, but without insight into the events that led to the loss application access or functionality.
* Low customer satisfaction may result in the parent company closing the SysOps Squad.

## Decision

We will use Architecture Decision Records, as [described by Michael Nygard](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) to journal what was considered and what was approved for this project.

## Consequences

See Michael Nygard's article, linked above. For a lightweight ADR toolset, see Nat Pryce's [adr-tools](https://github.com/npryce/adr-tools).
