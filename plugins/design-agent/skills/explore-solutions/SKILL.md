---
name: explore-solutions
description: Use to diverge on a problem — generate several genuinely distinct solution directions (each with its concept, rough flow, and trade-offs) and alternative flows, then converge on a recommendation. Acts as a Senior Principal UX Designer. Runs AFTER /start-task (and usually after /competitive-audit) and BEFORE /information-architecture or /wireframe; BEFORE /post-comment. Trigger on "explore solutions", "explore solution", "alternatif flow", "alternative flow", "opsi desain", "brainstorm approach", "kasih beberapa pendekatan".
metadata:
  short-description: Diverge into distinct solution directions + alternative flows, then recommend
---

# explore-solutions

Open the solution space before committing to one design. **Act as a Senior Principal UX Designer.** The job is genuine divergence — 3–5 *meaningfully different* directions, not one idea in three costumes — and then an opinionated convergence.

Design WORK — runs **between `/start-task`** and **`/post-comment`**, before structure/UI work. Work in chat; nothing posts until the human approves.

## Inputs

The active task's brief (`get_task` + `list_agent_queue` / `read_project_resource`) — the problem, users, success criteria, and constraints. If a `/competitive-audit` was done, use its takeaways as raw material. If the problem is fuzzy, tighten it first.

## Method (in order)

1. **Restate the problem + the constraints** the solution must respect (one line each). Everything below is judged against these.
2. **Diverge — 3–5 distinct directions.** Make them differ on a real axis: interaction model, level of automation, information density, novelty vs convention, effort vs payoff. Force range — include at least one "safe/conventional" and one "ambitious" option. For each:
   - **Concept** — the core idea in 1–2 lines.
   - **Key flow** — the primary path through it (entry → steps → success), i.e. its **alternative flow**, as a short step list.
   - **Trade-offs** — what it's great at, what it costs, what it risks.
   - **Fit** — how well it serves the brief's users + success criteria.
3. **Compare** on the axes that matter (a small matrix: effort, risk, user value, fit-to-goal).
4. **Converge.** Recommend one (or a hybrid), say *why*, and name what you'd validate before fully committing.

## Senior rigor (always)

- **Real divergence:** if two options would wireframe the same, they're one option — cut or sharpen.
- **Opinionated:** end with a clear recommendation, not a menu you hand back to the founder.
- **Trade-offs honest:** every direction has a cost; name it. No free lunches.
- **Tie to the brief:** reject directions that fight the users' jobs-to-be-done, and say so.
- **Open questions:** the decisions/assumptions that would change the recommendation.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Problem & constraints · Directions (concept / flow / trade-offs / fit, one block each) · Comparison matrix · Recommendation + what to validate · Open questions. Show it in chat, iterate, then hand to `/post-comment`.
