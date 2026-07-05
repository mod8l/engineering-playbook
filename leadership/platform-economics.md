# Platform Economics

A platform team is an investment, not a cost center. But it only pays for itself if it is timed, scoped, and measured correctly. This page covers the economics of platform work for ML startups: when to build, when to buy, and how to prove return on investment.

## When a platform team pays for itself

A platform team makes sense when the cost of not having one exceeds the cost of building it. That cost shows up as duplicated work, slow delivery, production incidents, and runaway infrastructure spend.

I look for three signals before recommending a dedicated platform team:

1. **Duplication tax.** Two or more product teams are solving the same infrastructure problem.
2. **Velocity tax.** Product teams spend more time on plumbing than on user-facing value.
3. **Reliability tax.** Incidents and outages repeatedly trace back to missing platform capabilities.

If only one signal is present, a platform seed or embedded platform engineer is usually enough.

## The platform investment formula

Estimate the annual value of a platform team:

```text
Platform value = (duplication savings) + (velocity savings) + (reliability savings) + (infrastructure savings)
```

Where:

- **Duplication savings** = engineer-hours not spent rebuilding the same system, multiplied by loaded cost.
- **Velocity savings** = faster time-to-market for dependent features, valued as revenue acceleration.
- **Reliability savings** = avoided incident cost, including customer churn and engineering time.
- **Infrastructure savings** = reduced cloud or inference spend through optimization.

If platform value is less than 1.5× the fully loaded cost of the platform team, the case is weak.

## Inference cost models

Inference is often the second-largest line item in an ML startup's cloud bill. Model it explicitly.

| Cost driver | How it scales | Optimization lever |
|-------------|---------------|--------------------|
| Request volume | Linear with usage | Caching, batching, quantization |
| Model size | Super-linear with memory and latency | Distillation, smaller models, model selection |
| Latency target | Tighter targets need more expensive hardware | Async processing, tiered serving |
| Concurrency | Determines required compute footprint | Auto-scaling, spot/preemptible instances |
| Provider markup | Managed APIs charge premium | Self-hosting when volume justifies it |

### Example: build-vs-host inference

| Option | Best for | Cost pattern | Hidden costs |
|--------|----------|--------------|--------------|
| Managed API (e.g., OpenAI, Anthropic) | Prototyping, variable volume, state-of-the-art needs | Per-token or per-request | Egress, rate limits, latency |
| Managed inference endpoint | Steady volume, need isolation | Per-hour or per-request | Provider lock-in, limited optimization |
| Self-hosted on cloud GPUs | High volume, latency-sensitive, cost-sensitive | Compute + ops overhead | Engineering time, reliability, scaling |
| Self-hosted on-prem or reserved capacity | Very high volume, long-term commitment | Capital or reserved spend | Maintenance, depreciation, flexibility |

## GPU utilization math

GPU utilization is the simplest lever for inference cost.

```text
effective_cost_per_hour = hourly_gpu_cost / utilization_rate
```

A GPU at 30% utilization costs 3× more per unit of work than the same GPU at 90%.

| Utilization | Effective cost multiplier | Typical cause |
|-------------|---------------------------|---------------|
| 10% | 10× | Massive over-provisioning |
| 30% | 3.3× | Uncoordinated auto-scaling |
| 60% | 1.7× | Reasonable for variable workloads |
| 85%+ | ~1.2× | Well-optimized batch or streaming workload |

Ways to improve utilization:

- Batch requests where latency allows.
- Use request pooling and dynamic batching.
- Schedule training and inference on shared fleets where feasible.
- Right-size instances instead of defaulting to the largest GPU.

## Engineer-hours saved

The most defensible platform ROI comes from engineer time. Track it honestly.

| Before platform | After platform | Hours saved per team per quarter |
|-----------------|----------------|----------------------------------|
| Build custom feature pipeline | Reuse platform feature store | `[X]` |
| Manual model deployment | Automated model registry deployment | `[Y]` |
| Debug inference without observability | Use platform dashboards and tracing | `[Z]` |
| Maintain separate serving stacks | Use shared inference platform | `[W]` |

Multiply saved hours by fully loaded engineering cost. Add a discount for optimism. I typically use a 50% confidence discount for first-year platform work.

## Build-vs-buy math

For each platform capability, estimate:

```text
build_cost = engineering_hours × loaded_cost + ongoing_maintenance + opportunity_cost
buy_cost = vendor_fee + integration_cost + lock_in_risk_premium
```

Use buy when:

- The capability is undifferentiated.
- Time-to-value matters more than unit cost.
- Vendor quality is high and lock-in is manageable.

Use build when:

- The capability is a competitive advantage.
- Existing products do not fit your constraints.
- You have the engineering capacity and domain expertise.

## When platform does not pay off

A platform team fails to pay for itself when:

- It is created before product teams need it.
- It builds generic abstractions nobody asked for.
- It is measured by output (tickets closed, features shipped) instead of outcome (time saved, cost reduced).
- It operates as a gatekeeper rather than an enabler.

I have seen platform teams consume a quarter of R&D headcount while product teams maintained parallel shadow systems. That is not platform; that is empire-building.

## Bracketed placeholders

- `[PLATFORM_TEAM_SIZE]` — number of engineers on the platform team.
- `[LOADED_ENGINEERING_COST]` — fully loaded annual cost per engineer.
- `[CURRENT_INFERENCE_SPEND]` — monthly or annual inference spend.
- `[GPU_INSTANCE_TYPE]` — primary GPU instance used.
- `[UTILIZATION_TARGET]` — target utilization percentage.
- `[PRIMARY_VENDOR]` — current managed inference or cloud provider.

## Further reading

- [R&D Org Design](rd-org-design.md) — when to create a platform team.
- [Startup Scaling Playbook](startup-scaling-playbook.md) — when to containerize, add a model registry, and hire SRE.
- [R&D Metrics](rd-metrics.md) — metrics to track platform value.
