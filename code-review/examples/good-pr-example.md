# Good PR Example

This is a fictional example showing the PR template filled out well.

---

## Summary

Add a lightweight churn-risk feature store job that materializes daily aggregates of user engagement for the subscription-retention model.

## Related Issues / Tickets

- Closes #142
- Design doc: [Feature Store Migration RFC](https://example.com/rfc-0142)

## Changes

- Add `engagement_daily_aggregates` feature view.
- Backfill 90 days of historical data with idempotent Spark job.
- Add unit tests for aggregation logic and timestamp handling.
- Update model-serving code to read from feature store instead of ad-hoc SQL.

## Test Plan

- [x] Unit tests added or updated
- [x] Integration tests pass
- [x] Manual verification performed
- [ ] Edge cases considered — see discussion below

**Edge cases discussed:**

- Timezone handling: aggregations use UTC boundaries, matching existing reporting.
- Missing data: null engagement rows are forward-filled up to 7 days, then treated as zero.
- Backfill idempotency: job uses `INSERT OVERWRITE` partition semantics and was rerun twice without duplication.

## Rollout / Risk

- **Rollback plan:** Revert serving code to previous release; feature store backfill is additive and safe.
- **Feature flag:** yes — `use_feature_store_churn_features`
- **Affected services / components:** churn-prediction service, feature store materialization job
- **Expected user-facing impact:** none directly; model scores may shift slightly after cutover

## Checklist

- [x] Code follows the project's style guidelines
- [x] Self-review completed
- [x] Tests added or updated
- [x] Documentation updated if needed
- [x] No sensitive data or secrets committed
- [x] Metrics and observability added for production changes
