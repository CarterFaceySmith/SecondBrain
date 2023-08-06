The balancing of requests to service infrastructure, normally in a [[Cloud Computing]] context, it is important to distribute the requests in the most efficient manner.

Enables horizontal scaling.

## Static vs. Dynamic

- Static: No feedback
- Dynamic: Feedback on status
	- Subtypes: distributed, cooperative, non-cooperative, centralised, semi-distributed (mainly based around the [[Node]] behaviour and whether there is a central load balancer or not)

## Load Balancing Algorithms

- Class-aware: Based on classification of requests into sensitive, best-effort and undesired
- Content-aware: Based on request content
- Client-aware: Based on packet source