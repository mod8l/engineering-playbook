# Runbook Template

Use this template for production runbooks. One runbook per critical service, pipeline, or failure mode.

---

# Runbook: [Service or Failure Mode]

## Metadata

- **Owner:** [team or individual]
- **Severity when triggered:** [SEV1 / SEV2 / SEV3]
- **Related alerts:** [links to alert definitions]
- **Related dashboards:** [links to dashboards]

## Detection

How do we know this incident is happening?

- Alert: [alert name and threshold]
- Dashboard: [link]
- Customer report: [support channel or process]

## Impact

What does this break, and who cares?

- Affected users or services:
- Customer-facing symptoms:
- Business impact:

## Escalation

Who should be involved, and in what order?

1. [Primary on-call]
2. [Secondary on-call / team lead]
3. [Engineering manager or incident commander]
4. [External stakeholders: customer success, legal, comms]

## Mitigation

Step-by-step actions to stop the bleeding. Prefer safe, reversible actions.

1. [Action 1]
2. [Action 2]
3. [Action 3]

### Common Rollbacks

- Roll back to last known good release: [command or link]
- Disable feature flag: [flag name]
- Fail over to secondary region: [runbook link]

## Verification

How do we confirm the incident is resolved?

- [ ] Key metric restored to baseline
- [ ] Smoke tests pass
- [ ] Customer-impacting flows verified
- [ ] Stakeholders notified

## Communication

- **Incident channel:** [Slack channel or equivalent]
- **Status page update:** [yes/no and owner]
- **Customer communication:** [owner and template]

## Post-Incident

- Open a postmortem issue within [timeframe].
- Attach the incident timeline and any saved logs or graphs.
- Update this runbook if the mitigation steps changed.
