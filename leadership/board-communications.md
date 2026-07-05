# Board Communications

Boards do not care about your refactor, your new embedding model, or your clean architecture diagram. They care about risk, velocity, and money. An R&D leader who cannot translate engineering work into those terms will lose budget battles and credibility.

This page is a framework for presenting R&D health, risk, and investment asks to a board. It assumes a standard venture-backed startup board, but the principles apply to any governance setting.

## The board narrative in three sentences

Every R&D update should answer:

1. What did we ship that moved the business?
2. What could kill us, and what are we doing about it?
3. What do we need to invest in next, and why now?

If you cannot answer those three questions, do not open the spreadsheet.

## Sample 6-slide narrative

### Slide 1: Business outcomes R&D delivered

- Revenue-impacting launches: `[LIST]`.
- Customer-facing metrics moved: `[METRIC]` up/down `[X%]`.
- Operational improvements: `[EXAMPLE]`.

Keep this to outcomes the board has heard of. "Launched semantic search" is less powerful than "reduced support ticket resolution time by 30%."

### Slide 2: R&D health snapshot

Use a traffic-light dashboard.

| Area | Status | Notes |
|------|--------|-------|
| Delivery velocity | [GREEN/YELLOW/RED] | Sprint completion, time to production. |
| System reliability | [GREEN/YELLOW/RED] | SLO attainment, incident trend. |
| Talent | [GREEN/YELLOW/RED] | Hiring pace, retention, key-person risk. |
| Security | [GREEN/YELLOW/RED] | Open criticals, audit status. |
| Technical debt | [GREEN/YELLOW/RED] | Known blockers and remediation plan. |

### Slide 3: Risk heat map

| Risk | Likelihood | Impact | Mitigation | Owner |
|------|------------|--------|------------|-------|
| `[EXAMPLE: key model maintainer leaves]` | Medium | High | Cross-training, documentation, retention plan | `[NAME]` |
| `[EXAMPLE: inference costs exceed unit economics]` | Medium | High | Cost optimization sprint, pricing review | `[NAME]` |
| `[EXAMPLE: data pipeline has no lineage]` | High | Medium | Implement lineage in Q[N] | `[NAME]` |

Only show risks you are actively managing. A risk without an owner and a date is theater.

### Slide 4: Investment ask

| Ask | Cost | Timing | Expected outcome |
|-----|------|--------|------------------|
| `[EXAMPLE: hire ML platform team lead]` | $[X] / year | Q[N] | Reduce model deployment time from days to hours. |
| `[EXAMPLE: migrate to managed inference]` | $[X] / month | Q[N] | Cut p99 latency by 50% and improve availability. |
| `[EXAMPLE: security audit and SOC 2 prep]` | $[X] one-time | Q[N] | Unblock enterprise sales. |

Tie every ask to a business outcome. Boards fund outcomes, not initiatives.

### Slide 5: Roadmap for the next quarter

| Priority | Initiative | Success metric | R&D owner |
|----------|------------|----------------|-----------|
| P0 | `[INITIATIVE]` | `[METRIC]` | `[NAME]` |
| P1 | `[INITIATIVE]` | `[METRIC]` | `[NAME]` |
| P2 | `[INITIATIVE]` | `[METRIC]` | `[NAME]` |

Show what you are not doing. Scope discipline is a sign of mature leadership.

### Slide 6: Discussion questions

End with two or three questions for the board. This turns a report into a conversation.

- Are we comfortable with the trade-off between `[FEATURE]` velocity and `[DEBT]` reduction this quarter?
- Should we accelerate `[INVESTMENT]` given `[MARKET SIGNAL]`?
- What level of availability risk is acceptable while we validate `[NEW MARKET]`?

## Metrics board members actually care about

| Metric | Why it matters | Target conversation |
|--------|----------------|---------------------|
| Time from idea to production | Capital efficiency and competitive speed | Track trend, not absolute. |
| Revenue or usage tied to shipped features | Proof that R&D creates value | Link launches to metrics. |
| Gross margin on AI features | Whether the business model works | Include inference and data costs. |
| Availability and incident rate | Customer trust and retention | Trend over time. |
| Key-person dependency | Risk concentration | Names, not abstractions. |
| Open headcount and time-to-fill | Execution risk | Flag delays early. |

## Red flags to raise yourself

Boards respect leaders who surface bad news early. Here are the red flags I always raise myself rather than waiting for an investor to find them:

- **Single points of failure.** One engineer owns the critical model, pipeline, or infrastructure.
- **Flat or declining delivery velocity.** Not one bad sprint, but a sustained pattern.
- **Rising incident severity or frequency.** Especially incidents tied to model changes.
- **Cost growth outpacing usage growth.** Inference economics are deteriorating.
- **Key departures or retention risk.** Be specific about impact and mitigation.
- **Unaddressed security debt.** Especially before enterprise deals or audits.
- **Technical debt blocking a strategic bet.** Name the bet and the debt.

## What to avoid

- **Jargon dumps.** Explain "embedding" and "vector database" only if the business outcome depends on it.
- **Vanity metrics.** Lines of code, model accuracy in isolation, and sprint points do not impress boards.
- **Surprise asks.** If you need headcount next quarter, you should have previewed the case last quarter.
- **Defensiveness.** A missed milestone is data, not a moral failing. Present the root cause and the fix.

## Bracketed placeholders

- `[BOARD_DATE]` — date of the board meeting.
- `[QUARTER]` — current fiscal quarter.
- `[CEO_NAME]` — CEO name for alignment.
- `[CFO_NAME]` — CFO name for financial asks.
- `[PRIMARY_RISK_1]` — the highest-impact risk this quarter.
- `[INVESTMENT_ASK_1]` — the top ask.

## Further reading

- [R&D Metrics](rd-metrics.md) — a fuller metrics dashboard.
- [Technical Due Diligence](technical-due-diligence.md) — what investors will look at before a round.
- [R&D Org Design](rd-org-design.md) — how org structure affects board risk discussions.
