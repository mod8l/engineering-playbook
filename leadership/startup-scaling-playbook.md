# Startup Scaling Playbook

Most ML startups die in the gap between a convincing demo and a reliable product. The demo gets funded; the product never ships. This playbook is the map I use to close that gap.

It covers architecture, build-vs-buy decisions, SLOs, containerization, model registry, and security/SRE hiring. It is written for teams from prototype to production.

## The MVP architecture

At the MVP stage, optimize for learning speed, not elegance.

| Layer | Recommendation | Rationale |
|-------|----------------|-----------|
| Model | Start with a hosted API or fine-tuned open-weight model | Do not train from scratch unless training data is your moat. |
| Serving | Serverless or managed inference endpoint | Scaling to zero keeps burn low during validation. |
| Data | Object storage + simple ETL in notebooks or scripts | Schema will change weekly. Avoid heavy pipelines. |
| Application | Monolith with clear module boundaries | Refactoring later is cheaper than distributed debugging now. |
| Frontend | Whatever gets the demo in front of users fastest | UX matters more than framework purity. |
| Observability | Logging and basic request metrics | You cannot improve what you cannot see. |

I tell founders: **"Buy every ounce of undifferentiated infrastructure you can. Moat lives in data and workflow, not in Kubernetes."**

## Build vs buy vs partner

| Capability | Build | Buy | Partner |
|------------|-------|-----|---------|
| Foundation model | Only if model architecture is core IP | Foundation model APIs or managed fine-tuning | University or research lab collaboration |
| Inference serving | Only if latency/cost are differentiated | Managed endpoints or serverless inference | CDN or edge provider for global low latency |
| Vector database | Only if you have unusual scale or query patterns | Managed vector DB | Existing data platform vendor |
| Feature store | Only after three teams need the same features | Managed feature platform | None; this is usually internal |
| Experiment tracking | Only if existing tools violate constraints | Weights & Biases, MLflow, Neptune | None |
| Data labeling | Build tooling only if labeling is continuous and strategic | Labeling services or crowdsourcing | Domain expert contractors |
| Security baseline | Build policy; buy tooling | Snyk, GitHub Advanced Security, cloud-native tools | External security audit before major raise |
| CI/CD | Build pipelines on top of GitHub/GitLab | GitHub Actions, GitLab CI | None |

Default bias: **buy for speed, build for differentiation, partner for access you cannot buy.**

## Maturity timeline

| Phase | Goal | Headcount | Key deliverables |
|-------|------|-----------|------------------|
| 0–3 months | Validate product-market fit | 1–3 | Demo, first paying or committed users, baseline metrics. |
| 3–6 months | Stabilize the happy path | 3–6 | Automated training pipeline, model evaluation on every change, first SLOs. |
| 6–12 months | Scale to production load | 6–15 | Containerized serving, model registry, feature reuse, basic incident response. |
| 12–24 months | Industrialize delivery | 15–40 | Dedicated platform team, multi-region or multi-cloud strategy, security program, cost optimization. |
| 24+ months | Optimize and expand | 40+ | Research lab, advanced SRE, data governance, external partnerships. |

## First SLOs

Define SLOs as soon as real users depend on the product. Start small and make them real.

| SLO | Target | Measurement |
|-----|--------|-------------|
| Availability | 99.9% over 30 days | Successful responses / total requests. |
| Latency (p50) | < 200 ms | End-to-end request duration. |
| Latency (p99) | < 1,000 ms | End-to-end request duration at tail. |
| Model freshness | < 7 days | Time since last successfully deployed model. |
| Prediction error rate | < 0.1% | Predictions that return errors or fall back to default. |

Set error budgets. If you burn the budget in a week, freeze feature launches and fix reliability.

## When to containerize

Containerize when:

- More than one person deploys the same service.
- Local behavior differs from production behavior.
- You need reproducible model training environments.
- You are preparing for CI/CD automation.

Do not containerize if:

- The entire system fits in one notebook.
- Your only deployment target is a managed notebook or serverless function.

## When to add a model registry

A model registry becomes necessary when:

- You have more than one model in production.
- You need to roll back a model without redeploying code.
- You want to track which model was live during an incident.
- Multiple teams or pods share models.

If you only have one model and deploy it with every release, a model registry is overhead. Start with versioned artifacts in object storage and a deployment log.

## When to hire SRE / security

| Signal | Hire |
|--------|------|
| On-call is burning people out. | SRE or senior backend with ops focus. |
| Incidents recur with the same root cause. | SRE with incident-management accountability. |
| Customers ask for SOC 2, ISO 27001, or penetration tests. | Security engineer or fractional CISO. |
| Inference spend exceeds 15% of cloud bill. | Platform engineer with cost-optimization focus. |
| You are preparing for a major fundraise or enterprise sales. | Security lead + external audit. |

I prefer to hire the first SRE as a senior backend engineer who has been on call, not as a pure operations specialist. They need credibility with the product team.

## Architecture checklist

Use this before each growth phase.

- [ ] Can a new engineer deploy a model change in under an hour?
- [ ] Can you roll back any model or code change in under ten minutes?
- [ ] Do you know the cost per prediction for each model?
- [ ] Do you have an incident response process with a defined owner?
- [ ] Are secrets and model artifacts encrypted at rest and in transit?
- [ ] Is training data versioned and reproducible?
- [ ] Do you have a data retention and deletion policy?

## Common traps

- **Over-engineering the MVP.** A beautiful microservices diagram does not validate a market.
- **Under-engineering post-PMF.** Once customers depend on you, reliability is a feature.
- **Hiring specialists before generalists.** A Kubernetes expert at three engineers is a distraction.
- **Ignoring cost until it is painful.** Cost per prediction should be tracked from the first paid tier.

## Bracketed placeholders

- `[PRIMARY_SLO_TARGET]` — e.g., `99.9%` availability.
- `[MODEL_REGISTRY_TOOL]` — e.g., `MLflow`, `Weights & Biases Model Registry`, `custom`.
- `[INFERENCE_PROVIDER]` — e.g., `AWS SageMaker`, `OpenAI API`, `Hugging Face Inference Endpoints`.
- `[SECURITY_FRAMEWORK]` — e.g., `SOC 2 Type II`, `ISO 27001`.
- `[COST_PER_PREDICTION_TARGET]` — target cost per prediction in currency units.

## Further reading

- [R&D Org Design](rd-org-design.md) — team topology at each stage.
- [Platform Economics](platform-economics.md) — cost models and build-vs-buy math.
- [R&D Metrics](rd-metrics.md) — what to measure as you scale.
- [Incident Response](../incident-response/) — runbooks and postmortems.
