# R&D Org Design

Org design is the most expensive decision an R&D leader makes because it is hard to undo. The right topology at ten engineers becomes a straitjacket at fifty. I have seen startups stall because they copied a FAANG org chart too early, and I have seen them stall because they refused to split responsibilities until the chaos became fatal.

This page gives pragmatic team topologies for ML startups at 0, 10, 25, and 50 engineers. The goal is to optimize for shipping value, not for elegance.

## Guiding principles

- **Product teams own outcomes; platform teams own capabilities.** Product teams deliver user-facing value. Platform teams make that delivery faster, cheaper, and safer.
- **Keep ML research close to production until it hurts.** A wall between research and engineering is a reliable predictor of models that never ship.
- **Platform is a product, not a service desk.** Internal customers are still customers. Platform teams need priorities, roadmaps, and feedback loops.
- **Hire generalists first, specialists when the volume justifies it.** A specialist hired too early invents work to stay busy.

## Team topology by stage

| Stage | Headcount | Topology | Key roles |
|-------|-----------|----------|-----------|
| 0 engineers | 0 | Founders do everything. Code, data, model, demos, and customer calls are the same person. | Technical founder or founding engineer. |
| 10 engineers | ~10 | One cross-functional pod owns the full ML lifecycle. No separate ML platform team. | Product manager, full-stack ML engineer, backend engineer, data engineer or analyst. |
| 25 engineers | ~25 | Product pods plus a nascent platform group (1–2 platform engineers, not yet a full team). | Pod leads, senior ML engineer, platform engineer, SRE or senior backend with ops ownership. |
| 50 engineers | ~50 | Product pods, a dedicated ML platform team, and an enablement function (data, tooling, SRE). | VP R&D or CTO, engineering managers, staff platform engineer, staff ML engineer, SRE lead, data/platform PM. |

## 0 engineers: the founder mode

At this stage the goal is learning, not scale.

- One person owns the model, the data pipeline, and the prototype UI.
- Use notebooks, spreadsheets, and hosted APIs freely. Infrastructure debt is cheap; missed market signal is expensive.
- Do not containerize yet. Do not build a feature store yet. Ship a demo that proves value.

I tell founders at this stage: **"Your job is to find a customer who cares, not a stack that impresses."**

## 10 engineers: the single pod

The first real R&D team should be a single cross-functional pod that owns the whole ML lifecycle.

| Responsibility | Owner |
|----------------|-------|
| Model prototyping | Senior ML engineer |
| Training pipeline | Same senior ML engineer, with backend support |
| Serving and inference | Backend engineer |
| Data collection and labeling | Data engineer or analyst |
| Product integration | Product manager + full-stack engineer |
| Reliability | Everyone; on-call rotates across the pod |

Why one pod works at this stage:

- Communication bandwidth is high.
- Everyone feels production pain.
- There is no "research team" that throws models over a wall.

The first platform hire is usually a senior backend engineer who cares about reliability and tooling. They are not called "platform" yet. They still ship user-facing features 50% of the time.

## 25 engineers: the platform seed

At ~25 engineers, the single pod splits. Product teams form around user journeys or model domains. A small platform group emerges to stop the same problem from being solved five times.

| Team | Focus | Typical size |
|------|-------|--------------|
| Product pod A | Core ML product experience | 4–6 engineers |
| Product pod B | Adjacent product surface or customer segment | 4–6 engineers |
| Platform seed | Inference serving, observability, feature reuse, experimentation tools | 1–2 engineers |
| Data/Analytics | Data quality, labeling, lineage, dashboards | 1–2 engineers |

### When to create the platform seed

Create it when you observe at least two of these signals:

- Two product pods are building overlapping inference infrastructure.
- Model deployments require manual steps that block releases.
- Inference costs are rising faster than usage.
- Incident root causes repeatedly point to observability gaps.

Do not create it because you admire another company's org chart.

## 50 engineers: the dedicated platform team

By fifty engineers, platform should be a real team with its own roadmap and internal customers.

| Team | Focus | Typical size |
|------|-------|--------------|
| Product pods (2–4) | End-to-end product outcomes | 5–8 each |
| ML Platform | Model registry, feature platform, training/serving orchestration, cost optimization | 4–6 |
| Data Platform | Data pipelines, quality, lineage, governance | 2–4 |
| Site Reliability / Production Engineering | SLOs, incident response, security baseline, cost observability | 2–4 |
| R&D Enablement | Developer experience, tooling, onboarding | 1–2 |

### Reporting lines

There is no single right answer, but here is what I prefer:

| Function | Reports to | Rationale |
|----------|------------|-----------|
| Product engineering teams | VP R&D / CTO via engineering managers | Keeps product and engineering trade-offs aligned. |
| ML Platform | VP R&D / CTO, ideally with a staff or principal engineer as tech lead | Requires deep technical authority and cross-pod influence. |
| Data Platform | VP R&D / CTO, or jointly with a data/analytics leader if the company has one | Avoids splitting data ownership between R&D and business intelligence. |
| SRE / Production Engineering | VP R&D / CTO | Production health is an engineering accountability, not an afterthought. |

## Research vs production split

The classic mistake is splitting "research" from "engineering" too early. The second classic mistake is never splitting them at all.

| Stage | Split? | Rationale |
|-------|--------|-----------|
| 0–10 engineers | No | Researchers who do not ship lose touch with reality. |
| 10–25 engineers | Soft split within pods | One engineer may lead exploratory work, but the pod owns production. |
| 25+ engineers | Yes, but keep rotations | A research or applied science function can exist, but researchers must rotate into production teams periodically. |
| 50+ engineers | Formal Applied Research + ML Platform + Product ML | Research defines direction; platform scales delivery; product teams own outcomes. |

## Platform-as-a-product

A platform team that behaves like an internal consultancy will fail. Treat platform as a product:

- Publish a roadmap with quarterly objectives.
- Define internal customers and hold quarterly business reviews.
- Measure adoption, time saved, and incident reduction.
- Say no to one-off favors that do not serve the roadmap.

Internal customers should have a choice, even if that choice is "use the platform or maintain your own fork." Choice creates accountability.

## Bracketed placeholders

Use these placeholders when adapting this page to your company:

- `[COMPANY_NAME]` — your company name.
- `[CURRENT_HEADCOUNT]` — current R&D headcount.
- `[PRIMARY_PRODUCT_POD_NAME]` — name of your first product pod.
- `[PLATFORM_TEAM_NAME]` — internal name for the platform team, e.g., `ML Platform` or `Foundation`.
- `[SRE_TEAM_NAME]` — name of the production engineering or SRE function.
- `[VP_RND_OR_CTO_NAME]` — R&D executive who owns the topology.

## Common anti-patterns

- **Hiring a VP of AI Research at ten engineers.** You need a head of product engineering who can model, not a research lab director.
- **Creating a platform team before any product team needs it.** Premature platform teams optimize for problems you do not have.
- **Letting every pod pick its own stack indefinitely.** Some divergence is healthy; uncontrolled divergence is expensive.
- **Reporting data platform to a non-technical function.** Data is infrastructure. It belongs in R&D.

## Further reading

- [Startup Scaling Playbook](startup-scaling-playbook.md) — when to add tooling and processes as you grow.
- [Platform Economics](platform-economics.md) — how to justify platform investment.
- [R&D Metrics](rd-metrics.md) — what to measure as the org scales.
