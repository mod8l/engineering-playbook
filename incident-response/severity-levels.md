# Severity Levels

Use these definitions to triage incidents consistently. Severity is driven by customer impact and business risk, not by how noisy the alert is.

## SEV1 — Critical

**Definition:** Complete outage or severe degradation affecting all or most users. Immediate, sustained revenue or safety risk. Requires executive notification and all-hands response.

**Examples:**

- Production API down globally for more than a few minutes.
- Customer data exposed externally.
- Model serving harmful outputs at scale due to a safety failure.

**Response:** Page on-call and engineering leadership immediately. Establish an incident commander and a war room within minutes.

## SEV2 — Major

**Definition:** Significant degradation for a subset of users or a critical feature. Workarounds may exist but are painful. No immediate safety risk.

**Examples:**

- Search or recommendations returning empty results for a region.
- Batch inference pipeline failing, delaying daily reports.
- Major feature flag misconfiguration causing incorrect model routing.

**Response:** Page the owning team. Leadership notification within 30 minutes. Track publicly until mitigated.

## SEV3 — Minor

**Definition:** Localized issue with limited customer impact or a known workaround. Does not require paging the whole team.

**Examples:**

- A single canary showing elevated error rates.
- Dashboard lagging behind real time.
- Intermittent timeouts affecting fewer than 1% of requests.

**Response:** Handle during business hours. Document and fix within the sprint.

## SEV4 — Informational

**Definition:** Anomaly or near-miss with no current customer impact. Used for tracking, capacity planning, or postmortem-worthy close calls.

**Examples:**

- A redundant component failed over cleanly.
- A deployment was caught by canary analysis and rolled back automatically.
- A test alarm fired in a non-production environment.

**Response:** Log in incident tracker. Optional brief postmortem if there is a useful systems lesson.

## Severity Can Change

Do not let the initial severity label slow you down. If impact grows, escalate. If impact shrinks, downgrade and communicate the change in the incident channel.
