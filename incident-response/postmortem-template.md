# Postmortem Template

Use this template for blameless postmortems after any SEV1, SEV2, or notable SEV3/SEV4 incident.

---

# Postmortem: [Incident Title]

## Metadata

- **Incident ID:** [tracker ID]
- **Date:** [YYYY-MM-DD]
- **Severity:** [SEV1 / SEV2 / SEV3 / SEV4]
- **Duration:** [start time to resolution]
- **Owner:** [postmortem author]
- **Reviewers:** [team members who reviewed]

## Summary

Two or three sentences describing what happened and the final impact.

## Impact

- **Customers affected:** [number or description]
- **Services affected:** [list]
- **Data impact:** [if any]
- **Business impact:** [revenue, reputation, trust]

## Timeline

| Time (UTC) | Event | Source |
|------------|-------|--------|
| 00:00 | First alert fired | [alert link] |
| 00:05 | On-call acknowledged | [incident channel] |
| 00:12 | Mitigation started | [incident channel] |
| 00:34 | Service restored | [dashboard link] |
| 00:45 | Incident closed | [incident channel] |

## Root Cause

Explain the proximate cause and the contributing factors. Be specific but avoid blame.

- **Proximate cause:** [the trigger]
- **Contributing factors:** [design assumptions, process gaps, missing tests]
- **What went right:** [detection, response, or recovery that worked well]

## Lessons Learned

What did we learn about our systems, processes, or team?

1.
2.
3.

## Action Items

| Action | Owner | Due Date | Priority |
|--------|-------|----------|----------|
| | | | |
| | | | |

## Appendix

- Incident channel transcript
- Relevant logs, traces, or dashboards
- Customer communications
