# Responsible AI Checklist

Use this checklist before moving an AI-powered feature from experiment to production. Not every item applies to every system; document any intentional exclusions.

## Safety

- [ ] Failure modes are identified and mitigated (for example, hallucinations, harmful outputs, adversarial inputs).
- [ ] Guardrails or output filters are in place for high-risk content.
- [ ] Abuse scenarios have been considered and addressed where feasible.
- [ ] A kill switch or rollback path exists if the system behaves unexpectedly.

## Privacy

- [ ] Only necessary data is collected and used for training or inference.
- [ ] Sensitive data is anonymized, encrypted, or excluded as appropriate.
- [ ] Data retention and deletion policies are defined and followed.
- [ ] Vendor or partner data-use agreements are reviewed and documented.

## Bias and Fairness

- [ ] Training and evaluation data are representative of the target population.
- [ ] Subgroup performance is evaluated across relevant demographic or user segments.
- [ ] Disparate impact is measured and addressed if found.
- [ ] Annotators and evaluators are instructed to watch for biased labels.

## Transparency

- [ ] Users are informed when they are interacting with an AI system.
- [ ] Model limitations and intended use cases are documented.
- [ ] Decision logic is explainable enough for the use case and audience.
- [ ] Model cards or equivalent documentation are maintained.

## Human Oversight

- [ ] High-stakes decisions include a path for human review or appeal.
- [ ] Operators can override, disable, or roll back the system.
- [ ] Escalation paths are documented and tested.
- [ ] Feedback loops allow affected users or operators to report problems.

## Accountability

- [ ] Ownership of the AI system is assigned to a specific team or individual.
- [ ] Metrics and monitoring are in place to detect drift and degradation.
- [ ] Incidents involving the AI system are tracked and reviewed.
- [ ] The team has a plan to update or retrain the model over time.
