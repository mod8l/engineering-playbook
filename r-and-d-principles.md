# R&D Principles

This is the short manifesto I return to when I am unsure how to prioritize, hire, review, or recover from a bad day in production. It is not doctrine; it is a set of defaults that have held up across teams and domains.

## Fast Feedback Loops

I optimize for the time between an idea and evidence. Short feedback loops surface bad assumptions early, keep teams motivated, and reduce the cost of being wrong. That means small pull requests, frequent deployments, automated tests, tight local development cycles, and observability that tells you what is happening now, not yesterday. If a loop feels slow, I treat it as a bug and fix it before it becomes culture.

## Safe-to-Fail Experiments

Innovation dies when failure is punished. I want teams to run experiments that can be rolled back in minutes, measured in hours, and learned from in days. A safe-to-fail experiment has a clear hypothesis, a bounded blast radius, and a defined stopping condition. It is not recklessness dressed up as agility; it is disciplined exploration with guardrails.

## Docs-as-Code

Documentation that lives outside the engineering workflow rots. I put decisions, runbooks, architecture records, and experiment logs in version control, reviewed like code, and kept close to the systems they describe. Good docs are not a separate activity; they are part of shipping.

## Ownership

Ownership means a person or a team can answer three questions: What is this supposed to do? How do I know it is healthy? What do I do when it breaks? I prefer narrow, explicit ownership over vague shared responsibility. Shared ownership is often no ownership, and on-call pages need a clear owner at 3 a.m.

## Trunk-Based Development

I default to trunk-based development with short-lived feature branches. Long-lived branches accumulate risk, delay integration feedback, and encourage heroics at merge time. Pairing, mobbing, and feature flags help teams integrate continuously without destabilizing production.

## Learning from Incidents

Incidents are unplanned investments in organizational learning. I treat them as signals about system design, process gaps, and communication failures—not as opportunities to assign blame. A good postmortem answers what happened, why it happened, how we knew, and what we are changing. The best postmortems also ask what went right, because resilience is built on what already works.

## Final Note

These principles compete with each other. Fast feedback can conflict with thorough review; ownership can conflict with collaboration; safe-to-fail experiments can conflict with compliance. The art of leadership is holding the tension and choosing deliberately, every day, with the team and context in front of you.
