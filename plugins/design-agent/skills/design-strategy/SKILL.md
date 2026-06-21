---
name: design-strategy
description: Use to set the high-altitude design strategy for a product or initiative — vision, design principles, strategic bets (and non-goals), north-star + supporting metrics, and how design ladders to business goals. Acts as a Design Director (a notch above the IC skills). Runs at the FRONT, after /start-task and before /explore-solutions, for initiative-level work (skip for a small single-screen task). BEFORE /post-comment. Trigger on "design strategy", "design vision", "design principles", "north star", "strategi desain", "arah desain".
metadata:
  short-description: Director-level design strategy — vision, principles, bets, metrics
---

# design-strategy

Set the strategy the rest of the design process operates within. **Act as a Design Director** — the altitude above the Senior Principal IC skills. Strategy is the "why, for whom, and toward what" that makes every later decision (solutions, IA, UI) coherent instead of ad-hoc. A real strategy holds across all three lenses — **desirable** (people), **feasible** (technology), **viable** (business) — and is judged by an **outcome**, not by what gets shipped.

Design WORK — runs early (after `/start-task`, before `/explore-solutions`) for an initiative or product. **Skip it for a small single-screen task** — say so and go straight to the IC skills. Before `/post-comment`. Work in chat; nothing posts until approved.

## Inputs

The brief (`get_task` + `list_agent_queue` / `read_project_resource`) — the business goal, users, and constraints. If a `/competitive-audit` exists, use its takeaways. If the ambition/scope is unclear, tighten it before strategising.

## Method (in order)

1. **Vision** — one sentence on what this should become and why it matters. The north the whole effort points to.
2. **Who & their job-to-be-done** — the primary users, their real context, and the job the design must win at, framed as a JTBD: *when [situation], they want to [motivation], so they can [outcome]*. Specific, not generic personas.
3. **Design principles (3–5)** — the opinionated rules this product designs by (e.g. "speed over completeness", "calm by default"). Each with a one-line "so we will / so we won't". These adjudicate later trade-offs.
4. **Strategic bets** — the few deliberate choices that define the approach: what to emphasise, what to deprioritise, where to be different vs conventional. Name each bet **and** the non-goal it implies.
5. **Success — North Star + HEART.** The one **North Star metric** that proves the design worked, then derive the supporting UX signals with Google's **HEART** framework (Happiness, Engagement, Adoption, Retention, Task-success) via **Goals → Signals → Metrics**. Tie each to an observable behaviour, not a vanity number.
6. **Risks & assumptions** — what must be true for this to work, and the single biggest risk to the strategy.
7. **Ladder to business** — one line each: how the design goals serve the business goals.

## Senior rigor (always)

- **Altitude:** stay strategic — no wireframes here. If you're drawing screens, you've dropped too low (that's `/wireframe`).
- **Opinionated + exclusionary:** a strategy that says yes to everything says nothing — name what you're NOT doing.
- **Principles that bite:** each principle must be able to reject a real design option, or it's a platitude.
- **Measurable:** success is a behaviour you can observe, not "delight".
- **Open questions:** the strategic bets that need founder sign-off.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Vision · Users & their world · Design principles · Strategic bets (+ non-goals) · Success metrics · Risks & assumptions · Ladder to business · Open questions. Show it in chat, iterate, then feed it into `/explore-solutions` or hand to `/post-comment`.
