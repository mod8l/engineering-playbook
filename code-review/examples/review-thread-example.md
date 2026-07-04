# Review Thread Example

A fictional, constructive review thread on the churn feature store PR.

---

**Author:** Alex Chen  
**Reviewer:** Jordan Patel

## Thread

**Jordan:** `consider` — The 7-day forward-fill for missing engagement feels reasonable for active users, but for users who churned and returned, we might incorrectly inflate their recent signal. Could we add a test case for that pattern and document the assumption in the feature view docstring?

**Alex:** Good catch. I added a test for the churn-and-return case and updated the docstring to explain the 7-day cap and when it breaks down. Let me know if the wording is clear.

**Jordan:** Wording is clear. One follow-up `must fix`: the integration test only covers UTC users. Our user base spans three timezones, and daily aggregates by UTC could misattribute late-night sessions. Can we add a parameterized test for PST and JST boundaries?

**Alex:** Done. I parameterized the test across UTC, PST, and JST, and confirmed the 7-day rolling window respects local midnight. I also noted in the PR description that model scores may shift slightly because of this change.

**Jordan:** Approved. The rollout plan and feature flag give us a clean escape hatch. Nice work.

---

## Why This Works

- The reviewer separates a preference (`consider`) from a blocker (`must fix`).
- Both parties explain the why behind the concern.
- The author updates the PR description with new information surfaced during review.
- The tone stays collaborative and focused on the code.
