# Interview Loop

I run interviews this way because the goal is not to stump candidates; it is to gather calibrated signal on the competencies that predict success in the role.

This loop assumes a Staff/Principal ML Engineer position. Adjust depth and emphasis for more junior or more specialized roles.

## Overview

| Session | Duration | Interviewer(s) | Focus |
|---------|----------|----------------|-------|
| Hiring Manager | 45-60 min | Hiring manager | Motivation, scope fit, career trajectory |
| System Design | 60 min | Senior engineer/staff+ | ML system design, trade-offs, operational thinking |
| Coding / ML | 60 min | ML engineer | Code, model implementation, debugging, data judgment |
| Behavioral | 45 min | Cross-functional partner | Collaboration, ownership, learning from failure |

## 1. Hiring Manager Screen

### Goals

- Confirm alignment on role scope, level, and working style.
- Understand the candidate's career narrative and what they want next.
- Sell the team and the work honestly.

### Scorecard

| Dimension | Strong signal | Weak signal |
|-----------|-------------|-------------|
| Motivation | Has specific reasons that map to this role | Vague or purely transactional |
| Scope fit | Comfortable with ambiguity and cross-team impact | Wants fully scoped tasks only |
| Communication | Clear, structured, self-aware | Rambling, evasive, or overly scripted |

### Anti-patterns

- Overselling the role.
- Asking brain teasers or trivia.
- Cutting the screen short when the candidate is quiet; some people need a minute to warm up.

## 2. System Design

### Goals

- Assess ability to design a real-world ML system end to end.
- Surface trade-offs between accuracy, latency, cost, maintainability, and fairness.

### Prompt example

"Design a system that recommends content to users in real time. Walk me through data collection, feature engineering, model selection, serving, evaluation, and rollout."

### Scorecard

| Dimension | Strong signal | Weak signal |
|-----------|-------------|-------------|
| Problem framing | Clarifies requirements and constraints | Jumps to a solution without scoping |
| Data judgment | Discusses leakage, bias, freshness, lineage | Treats data as a static given |
| Operational design | Discusses monitoring, rollback, observability | Ignores failure modes |
| Trade-offs | Compares options explicitly | Claims one approach is best in all cases |

### Anti-patterns

- Letting the candidate drift into a research proposal instead of an engineering design.
- Asking for exact numbers the candidate cannot know.
- Evaluating on speed of drawing boxes rather than clarity of thinking.

## 3. Coding / ML

### Goals

- Evaluate hands-on ability to write clean, working code and reason about data.
- The best prompts are close to real tasks: feature transforms, model evaluation, debugging a training pipeline.

### Scorecard

| Dimension | Strong signal | Weak signal |
|-----------|-------------|-------------|
| Code quality | Readable, tested, modular | One-off scripts, no structure |
| ML judgment | Validates splits, checks metrics, spots leakage | Chases leaderboard scores blindly |
| Debugging | Methodically isolates issues | Guesses and changes things at random |
| Collaboration | Thinks aloud, accepts hints | Goes silent or defensive |

### Anti-patterns

- Live-coding theater where the interviewer watches in silence.
- Problems that require memorized tricks.
- Evaluating whether the candidate finishes in time rather than how they reason.

## 4. Behavioral

### Goals

- Understand how the candidate works with others under pressure.
- Probe ownership, resilience, and growth mindset.

### Prompts

- Tell me about a time you inherited a messy system. What did you do first?
- Describe a project that failed. What did you learn?
- How do you handle a strong disagreement with a peer about technical direction?
- When have you changed your mind because of feedback?

### Scorecard

| Dimension | Strong signal | Weak signal |
|-----------|-------------|-------------|
| Ownership | Takes responsibility for outcomes | Blames circumstances or other teams |
| Collaboration | Builds trust across roles | Dismisses non-engineering partners |
| Growth | Reflects honestly on mistakes | Presents every story as a victory |

### Anti-patterns

- Accepting polished STAR stories without follow-up.
- Confusing confidence with competence.
- Letting one bad behavioral signal override strong technical signal, or vice versa.

## Debrief

- Each interviewer shares evidence, not just a thumbs up or down.
- We separate "hired at the target level" from "hired at a different level" from "not hired."
- One strong dissent is enough to slow down an offer. Groupthink in hiring is expensive.
