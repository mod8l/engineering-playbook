# Experiment Log Template

Use this template to log AI experiments. A good experiment log makes it easy to compare attempts, reproduce results, and decide whether to scale or stop.

---

# Experiment: [Short Name]

## Metadata

- **Experiment ID:** [unique identifier]
- **Date:** [YYYY-MM-DD]
- **Owner:** [name]
- **Status:** [planned / running / completed / stopped / scaled]

## Hypothesis

We believe that [change] will improve [outcome] for [population] because [reasoning].

## Problem and Success Criteria

- **Business problem:** [what user or business outcome are we trying to improve?]
- **Primary metric:** [the metric that decides success]
- **Secondary metrics:** [other metrics we will watch]
- **Guardrail metrics:** [metrics that must not degrade]
- **Minimum detectable effect:** [what change is meaningful?]

## Data

- **Dataset:** [name, version, source]
- **Time range:** [dates covered]
- **Preprocessing:** [key transformations]
- **Train / validation / test split:** [method and ratios]
- **Known limitations:** [leakage risks, label quality, coverage gaps]

## Model

- **Model family:** [e.g., gradient-boosted trees, transformer, LLM]
- **Architecture / version:** [specific model name or config]
- **Hyperparameters:** [key settings]
- **Training environment:** [hardware, framework versions]

## Results

### Offline Evaluation

| Metric | Value | Baseline | Notes |
|--------|-------|----------|-------|
| | | | |

### Online Evaluation (if applicable)

| Metric | Treatment | Control | Notes |
|--------|-----------|---------|-------|
| | | | |

## Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| | | | |

## Decision

- [ ] Scale to production
- [ ] Run a follow-up experiment
- [ ] Stop; not promising enough
- [ ] Pause; blocked by [reason]

## Decision Rationale

[Explain why the chosen decision is justified. Include caveats and open questions.]

## Follow-Up Actions

| Action | Owner | Due Date |
|--------|-------|----------|
| | | |
