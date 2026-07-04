# Take-Home Exercise

A two-hour ML system design exercise. It is intentionally open-ended so candidates can show judgment, not just implementation speed.

## Important Notes

- **No free work.** This prompt is fictional and self-contained. It is not a disguised feature request.
- **No production data.** Candidates should use synthetic or public data only.
- **Respect candidate time.** Two hours is a hard ceiling. We evaluate what they produce in that window, not a polished week-long project.
- **Accommodate schedules.** Offer a take-home alternative if a candidate prefers live collaboration due to time or accessibility constraints.

## Prompt

### Background

You are joining a company that operates a subscription learning platform. The product team wants to reduce churn by identifying users at risk of canceling their subscription in the next 14 days.

### Your Task

Design a machine learning system to predict churn risk and present your design in a short document (1-2 pages) plus any supporting code or diagrams you find useful.

Address the following:

1. **Problem framing.** How do you define the prediction target? What are the pros and cons of your definition?
2. **Data.** What features would you use? How would you handle class imbalance, leakage, and feature freshness?
3. **Model.** What model family would you start with, and why? How would you evaluate it offline?
4. **Serving.** How would you deliver predictions to the product? What latency and throughput constraints would you design for?
5. **Rollout.** How would you move from offline evaluation to a live intervention? How would you measure real-world impact?
6. **Risks.** What could go wrong, and how would you guard against it?

### Deliverables

- A written design document.
- Optional: a small notebook or script demonstrating a key idea (for example, a synthetic data generator, a baseline model, or an evaluation pipeline).

## Evaluation Rubric

| Dimension | Excellent (4) | Good (3) | Acceptable (2) | Below bar (1) |
|-----------|---------------|----------|----------------|---------------|
| Problem framing | Defines a clean, measurable target and discusses trade-offs | Clear target, minor gaps | Target is vague or unrealistic | Missing or misunderstood |
| Data judgment | Explicitly addresses leakage, imbalance, freshness, and ethics | Addresses most issues | Addresses one or two issues | Ignores data risks |
| Model & evaluation | Chooses appropriate baseline, defines offline metrics, and avoids over-engineering | Solid choices with minor gaps | Overly complex or under-specified | Inappropriate approach |
| Serving & rollout | Describes practical deployment, intervention, and measurement | Reasonable plan | Partial plan | No operational thinking |
| Communication | Clear, structured, and concise | Mostly clear | Hard to follow | Disorganized or incomplete |

## How We Review

- We do not expect production code. We look for clarity of thought and awareness of real-world constraints.
- We anonymize submissions before review where feasible to reduce bias.
- We provide written feedback to every candidate who completes the exercise.
