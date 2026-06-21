---
name: prioritization
description: Use to prioritise features/initiatives/backlog — score and rank with a real framework (RICE, impact-effort, or MoSCoW), then recommend what to do now vs next vs later. Acts as a Senior Product Manager. Runs when there's more to do than capacity; BEFORE /create-report. Trigger on "prioritization", "prioritise", "what should we build first", "rice", "backlog", "impact effort", "prioritas".
metadata:
  short-description: Score + rank work (RICE / impact-effort / MoSCoW) → now/next/later
---

# prioritization

Decide what to build first, defensibly. **Act as a Senior Product Manager.** Prioritisation is where strategy meets reality — saying no to good ideas so the best ones ship. Inherits the **principal-grade standard** — outcomes over outputs, explicit trade-offs.

Runs whenever there's more to do than capacity, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The list of candidates (features/initiatives/bugs), the goal they serve (North Star / OKR), and rough effort. If the goal is unclear, anchor it first — you can't prioritise without it.

## Method (in order)
1. **Pick the framework to fit the decision:**
   - **RICE** (Reach × Impact × Confidence ÷ Effort) — for comparing many items on impact-per-effort.
   - **Impact/Effort matrix** — for a quick quadrant read (quick wins vs big bets vs time-sinks).
   - **MoSCoW** (Must/Should/Could/Won't) — for scoping a release.
3. **Score honestly.** Estimate each input; mark low-confidence scores (don't fake precision).
4. **Rank + sanity-check.** Order by score, then sanity-check against strategy — the math informs, judgment decides.
5. **Recommend now / next / later**, and **what you're saying NO to** (and why).

## Senior rigor (always)
- **Tie to the goal** — every item scored against the outcome it drives, not gut feel.
- **Confidence is a real input** — a high-impact guess isn't a high priority.
- **Say no explicitly** — name what's deprioritised; an everything-list is no priority.
- **Judgment over the spreadsheet** — the score is an input, not the decision.
- **Open questions** — assumptions that would reorder the list.

## Output
A self-contained **HTML document**: the framework + scoring table, the ranked list, the now/next/later split, and what's deprioritised (with why). Hand to `/roadmap` or `/create-report`.
