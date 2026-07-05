# Technical Due Diligence

This framework is for investors, advisors, and executives evaluating an ML startup's technical readiness. It is also useful for founders who want to see themselves through an investor's lens before a fundraise.

I have used versions of this scorecard on both sides of the table. The best technical diligence is not an audit; it is a structured conversation that separates real engineering from good storytelling.

## Four pillars

Evaluate across four pillars: code, data, team, and production readiness. No single pillar is enough.

| Pillar | Questions | Sources |
|--------|-----------|---------|
| Code | Can the team ship and maintain quality software? | Git history, CI/CD, test coverage, architecture review. |
| Data | Is data a moat or a liability? | Data pipeline, lineage, quality checks, rights and licenses. |
| Team | Does the team have the right shape and depth? | Org chart, interviews, retention history, key-person risk. |
| Production readiness | Can the product run reliably at scale? | SLOs, observability, incident history, security posture. |

## The scorecard

Rate each area from 1 (critical risk) to 5 (strong). A 3 is acceptable but not a strength.

### Code

| # | Criterion | 1 | 3 | 5 |
|---|-----------|---|---|---|
| 1 | Version control and collaboration | Ad hoc or single-contributor | Git with basic PRs | Trunk-based or clean branching, thorough code review |
| 2 | CI/CD | Manual deployments only | Some automation, frequent failures | Reliable automated pipelines, can deploy on demand |
| 3 | Test coverage | None or only notebooks | Unit tests for core logic | Integration, contract, and model tests |
| 4 | Architecture clarity | Big ball of mud | Modular but inconsistent | Clear boundaries, documented interfaces |
| 5 | Documentation | Outdated or absent | Partial, maintained by one person | Living docs, runbooks, ADRs |

### Data

| # | Criterion | 1 | 3 | 5 |
|---|-----------|---|---|---|
| 6 | Data rights and licenses | Unclear or risky | Mostly clear, some gaps | Fully documented, legal review in place |
| 7 | Data quality checks | None | Ad hoc manual checks | Automated validation, anomaly detection |
| 8 | Data lineage | Unknown | Partially documented | End-to-end lineage for training and serving |
| 9 | Training/serving skew | Not measured | Measured but not fixed | Monitored and actively mitigated |
| 10 | Data as moat | Commodity data | Some proprietary data or feedback loops | Unique data asset that compounds |

### Team

| # | Criterion | 1 | 3 | 5 |
|---|-----------|---|---|---|
| 11 | Technical leadership | Inexperienced or absent | Capable but stretched | Strong VP/CTO with relevant scale experience |
| 12 | Research-to-production balance | Pure researchers or pure engineers | Some overlap, occasional handoffs | Engineers who can model and researchers who can ship |
| 13 | Key-person risk | Single founder holds everything | Some redundancy | Documented, cross-trained team |
| 14 | Hiring pipeline | No plan or no brand | Reactive hiring | Clear plan and proven ability to close |
| 15 | Culture and velocity | Bureaucratic or chaotic | Functional but uneven | High trust, high accountability |

### Production readiness

| # | Criterion | 1 | 3 | 5 |
|---|-----------|---|---|---|
| 16 | SLOs and monitoring | No SLOs, limited observability | Basic metrics, reactive alerting | Defined SLOs, error budgets, proactive alerts |
| 17 | Incident response | No process | Ad hoc, no follow-up | Runbooks, severity levels, blameless postmortems |
| 18 | Security baseline | No baseline | Some tooling, no program | Security program, access controls, audit readiness |
| 19 | Scalability | Unknown limits | Tested for current load | Load tested, capacity planned, cost modeled |
| 20 | Model operations | Manual model deployment | Versioned models, some automation | Model registry, A/B testing, rollback in minutes |

## Scoring guidance

- **80–100:** Strong technical foundation. Diligence should focus on scaling bottlenecks and team depth.
- **60–79:** Solid but with clear gaps. Identify which gaps are blockers for the next funding or revenue milestone.
- **40–59:** Material risks. Require a remediation plan before major investment or enterprise commitments.
- **20–39:** High risk. Consider whether the team can close the gap with available capital and time.
- **0–19:** Likely not investable on technical grounds alone.

I weight team and production readiness more heavily than code elegance at the earliest stages. A scrappy team that ships reliably is more valuable than a beautiful codebase that never reaches users.

## Key questions to ask the team

Use these questions in management interviews and architecture walkthroughs.

1. Walk me through the last production incident. What happened, how did you detect it, and what changed afterward?
2. How long does it take to deploy a model improvement from notebook to production?
3. What is your cost per prediction, and how is it trending?
4. What data do you have that a competitor cannot easily replicate?
5. Who would leave the biggest hole if they resigned tomorrow?
6. What technical debt are you deliberately carrying, and why?
7. How do you validate that a model change does not degrade the user experience?
8. What is your security posture around model artifacts and customer data?

## Red flags

- Cannot explain the architecture in plain language.
- No production monitoring or alerting.
- Model accuracy is the only success metric discussed.
- Founding engineer is the only person who can deploy.
- Data rights are "being sorted out."
- Every answer begins with "we will" rather than "we do."

## Bracketed placeholders

- `[COMPANY_NAME]` — target company.
- `[DILIGENCE_DATE]` — date of the assessment.
- `[LEAD_INVESTOR_NAME]` — lead investor or fund.
- `[CTO_OR_VP_NAME]` — technical leader interviewed.
- `[KEY_PRODUCT]` — product being evaluated.

## Further reading

- [R&D Metrics](rd-metrics.md) — metrics that support this scorecard.
- [Startup Scaling Playbook](startup-scaling-playbook.md) — how to close gaps found during diligence.
- [Board Communications](board-communications.md) — how to present findings to a board.
