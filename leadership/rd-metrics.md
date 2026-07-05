# R&D Metrics

Metrics shape behavior. If you measure model accuracy alone, you get a team that optimizes leaderboard scores while the product breaks in production. If you measure only shipping speed, you get brittle systems and burned-out engineers.

This page adapts DORA-style delivery metrics for ML teams and adds production, cost, and reuse metrics that matter for ML products.

## The metric hierarchy

| Level | Purpose | Example metrics |
|-------|---------|-----------------|
| Business outcomes | Did R&D move the company? | Revenue from shipped features, user engagement, gross margin. |
| Delivery health | Can the team ship reliably? | Deployment frequency, lead time for changes, change failure rate. |
| ML health | Are models healthy in production? | Model refresh cadence, prediction error rate, training-serving skew. |
| Operational health | Can the system run reliably? | Availability, latency, incident rate, MTTR. |
| Efficiency | Are we spending wisely? | Cost per prediction, GPU utilization, feature reuse. |

## DORA-style metrics adapted for ML

| Metric | Definition | Why it matters | Target |
|--------|------------|----------------|--------|
| Deployment frequency | How often model or code changes reach production | Measures batch size and risk | At least weekly for mature teams |
| Lead time for changes | Time from commit to production | Measures feedback loop speed | Under one week for code, under two weeks for model changes |
| Change failure rate | Percentage of releases causing incidents | Measures quality of release process | Under 5% |
| Time to recovery (MTTR) | Time to restore service after incident | Measures operational maturity | Under one hour for critical services |

## ML-specific metrics

| Metric | Definition | Why it matters | Target |
|--------|------------|----------------|--------|
| Time-to-first-inference | Time from a new idea to the first live prediction | Validates experimental velocity | Days, not months |
| Model refresh cadence | How often production models are retrained or updated | Prevents model staleness | Aligned with data drift, typically weekly to monthly |
| Training-serving skew | Difference between training and production feature distributions | Catches data pipeline bugs | Monitored and below threshold |
| Prediction error rate | Rate of failed or default predictions | Measures serving reliability | Below 0.1% |
| Data freshness | Age of the newest data feeding the model | Prevents stale decisions | Minutes to hours, depending on use case |
| Label quality | Accuracy or consistency of labels | Foundation of model quality | Measured and improving |

## Cost and efficiency metrics

| Metric | Definition | Why it matters | Target |
|--------|------------|----------------|--------|
| Cost per prediction | Total inference cost divided by prediction volume | Validates unit economics | Trending down or stable |
| GPU utilization | Percentage of GPU capacity used productively | Prevents waste | Above 60% for steady workloads |
| Feature reuse | Number of teams or models using the same feature | Measures platform leverage | Increasing over time |
| Engineer-hours saved by platform | Estimated hours platform tools save product teams | Justifies platform investment | Positive ROI within two quarters |

## Starter dashboard outline

Build a single-page dashboard that updates automatically. Review it weekly in the R&D leadership meeting.

### Top row: business outcomes

- Revenue influenced by shipped ML features: `[CHART]`.
- User-facing metric movement: `[CHART]`.
- Gross margin on AI features: `[CHART]`.

### Second row: delivery health

- Deployments per week: `[CHART]`.
- Lead time distribution: `[CHART]`.
- Change failure rate: `[CHART]`.

### Third row: ML health

- Model refresh cadence by model: `[TABLE]`.
- Training-serving skew alerts: `[LIST]`.
- Prediction error rate: `[CHART]`.

### Fourth row: operational health

- Availability by service: `[CHART]`.
- Incident count and severity: `[CHART]`.
- Mean time to recovery: `[CHART]`.

### Fifth row: efficiency

- Cost per prediction: `[CHART]`.
- GPU utilization: `[CHART]`.
- Feature reuse count: `[CHART]`.

## Using metrics without gaming them

Every metric can be gamed. Prevent gaming by pairing metrics.

| Good metric | Pair with | Why |
|-------------|-----------|-----|
| Deployment frequency | Change failure rate | High frequency is bad if it breaks things. |
| Lead time | Quality score or defect rate | Fast shipping is bad if it ships garbage. |
| Cost per prediction | Availability and latency | Cheap is bad if it is slow or broken. |
| Feature reuse | Time-to-first-inference | Reuse is bad if it forces teams into a slow platform. |

## Bracketed placeholders

- `[DASHBOARD_TOOL]` — e.g., `Grafana`, `Datadog`, `Looker`, `custom`.
- `[PRIMARY_BUSINESS_METRIC]` — the north-star metric R&D influences.
- `[COST_PER_PREDICTION_UNIT]` — e.g., cents per prediction.
- `[MODEL_LIST]` — list of production models.
- `[REVIEW_CADENCE]` — e.g., weekly.

## Anti-patterns

- **Reporting only vanity metrics.** Lines of code, sprint points, and model size do not prove value.
- **Optimizing one metric in isolation.** Always pair metrics.
- **Collecting metrics no one reviews.** If the dashboard is not used in a recurring meeting, kill it.
- **Punishing teams for metrics they do not control.** Metrics are for learning, not blame.

## Further reading

- [Platform Economics](platform-economics.md) — cost models behind the efficiency metrics.
- [Startup Scaling Playbook](startup-scaling-playbook.md) — when to start measuring each metric.
- [Board Communications](board-communications.md) — how to present these metrics to a board.
