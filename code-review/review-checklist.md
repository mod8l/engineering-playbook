# Review Checklist

Use this checklist during code review. Not every item applies to every change; use judgment and comment explicitly when you skip an item for good reason.

## General

- [ ] **Purpose is clear.** I understand what the change does and why from the PR description.
- [ ] **Scope is appropriate.** The PR is small enough to review thoughtfully in one sitting.
- [ ] **Tests cover the change.** Unit, integration, or manual tests are present and meaningful.
- [ ] **Error handling is explicit.** Failures are caught, logged, and handled rather than swallowed.
- [ ] **Observability is present.** Logs, metrics, or traces are added for production-relevant paths.
- [ ] **Security is considered.** Input validation, authz checks, and secret handling are appropriate.
- [ ] **Rollback is safe.** The change can be reverted without data loss or manual recovery steps.
- [ ] **Documentation is updated.** READMEs, API docs, or runbooks reflect the change.

## ML-Specific

- [ ] **Data leakage is ruled out.** Training and evaluation splits are created correctly; no future information leaks into training.
- [ ] **Reproducibility is documented.** Random seeds, environment versions, and data snapshots are pinned or recorded.
- [ ] **Evaluation metrics are appropriate.** Offline metrics match the business objective and are reported with confidence intervals or variance when possible.
- [ ] **Feature logic is consistent.** Training-time and serving-time feature computation match (training-serving skew is addressed).
- [ ] **Model artifacts are versioned.** Model weights, configs, and feature stores use identifiable versions.
- [ ] **Rollback plan exists.** A model can be reverted to a previous version quickly if metrics degrade.
- [ ] **Observability covers drift.** Production inputs, predictions, and outcomes are logged to detect data drift and concept drift.
- [ ] **Model card or model documentation is updated.** Intended use, limitations, and known failure modes are described.
- [ ] **Fairness and bias are considered.** Sensitive attributes are handled responsibly; subgroup metrics are reported where relevant.
- [ ] **Human oversight is designed in.** High-stakes predictions include escalation paths or human review.

## Review Tone

- [ ] Comments are framed as suggestions, not accusations.
- [ ] Blockers are clearly labeled as `must fix`.
- [ ] Preferences are labeled as `consider` or `nit`.
- [ ] The reviewer explained the why behind non-obvious requests.
