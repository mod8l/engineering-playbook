# Evaluation Framework

A simple decision matrix for choosing between building, buying, or partnering for an AI capability.

## Decision Matrix

Rate each criterion as low, medium, or high for your situation. Then compare the three paths.

| Criterion | Build | Buy | Partner |
|-----------|-------|-----|---------|
| **Data sensitivity** | You control everything, but you also own every risk. | Vendor handles infrastructure; verify their security posture. | Shared responsibility; requires clear data-use agreements. |
| **Latency** | Optimizable end to end. | Depends on vendor architecture and SLA. | Negotiable, but constrained by integration points. |
| **Cost** | High upfront, lower marginal cost at scale. | Predictable per-request or seat cost; can explode with scale. | Variable; includes licensing, integration, and ongoing relationship cost. |
| **Maintenance** | You own models, data pipelines, and drift monitoring. | Vendor owns the model; you own integration and validation. | Shared; clarify who re-trains, updates, and supports. |
| **Differentiation** | Highest potential if the capability is core to your product. | Low; competitors can buy the same API. | Medium; depends on what you add on top. |

## When to Choose Each

### Build

- The capability is core to your product or strategy.
- You have unique data, evaluation benchmarks, or constraints.
- You can afford the team and infrastructure to own the full lifecycle.

### Buy

- The capability is a commodity (for example, OCR, translation, generic summarization).
- Time to market matters more than differentiation.
- The vendor's SLA, security, and roadmap meet your needs.

### Partner

- The capability requires specialized research or data you do not have.
- You want co-development or shared IP.
- A pure vendor relationship is too rigid, but building alone is too expensive.

## Recommended Process

1. **Define success.** What does the capability need to achieve? Be specific.
2. **Score the criteria.** Use the matrix above with real constraints.
3. **Run a pilot.** Test the chosen path on a narrow, measurable use case.
4. **Re-evaluate.** Revisit the decision every [quarter / release cycle] as constraints change.

## Common Traps

- Building a commodity because "we are an engineering company."
- Buying without validating vendor claims on your own data.
- Partnering without a written exit plan and data-handling agreement.
