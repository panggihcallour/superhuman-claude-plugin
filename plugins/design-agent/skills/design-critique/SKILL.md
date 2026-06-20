---
name: design-critique
description: Use to critique a design rigorously — against the brief and goals, visual hierarchy, consistency, usability heuristics, accessibility flags, and content — producing prioritised, actionable issues, not vibes. Acts as a Senior Principal UX Designer. Runs as a QA gate AFTER a design exists and BEFORE /post-comment. Trigger on "critique", "design critique", "review this design", "kritik desain", "roast my design", "feedback on the design", "heuristic review".
metadata:
  short-description: Rigorous, prioritised design critique against brief, hierarchy, heuristics, a11y
---

# design-critique

Critique a design the way a senior reviewer would in a design crit. **Act as a Senior Principal UX Designer.** Be direct and specific — every point is observation → why it matters → suggested fix, and tied to the user's goals, not personal taste.

Design WORK — a QA gate that runs **after a design exists** and before **`/post-comment`**. Work in chat; nothing posts until the human approves.

## Inputs

The brief + success criteria (`get_task` + resources) — you critique *against the goal*, not in a vacuum. The design itself: an HTML/visual deliverable in chat, or a Figma file (use `figma_take_screenshot` / `figma_get_file_data` to see it precisely).

## Method (in order)

1. **Restate the goal.** The user, their job, and what success means — the yardstick for every comment.
2. **First impression (squint test).** Where does the eye land? Is the primary action obvious in 3 seconds? Note the gut read before analysing.
3. **Work the lenses:**
   - **Hierarchy & focus** — does emphasis match importance?
   - **Usability heuristics** — visibility of status, match to real world, user control, consistency, error prevention, recognition over recall, flexibility, minimalism, error recovery, help.
   - **Consistency** — type/space/color/component usage; one-offs.
   - **Content** — clarity, tone, scannability, labels (pointer to `/ux-writing`).
   - **States & edges** — are empty/loading/error designed, or only the happy path?
   - **Accessibility** — contrast, target size, focus, semantics (deep audit → `/wcag-check`).
4. **Prioritise.** Sort findings: **Blocker** (breaks the goal) · **Major** (real friction) · **Minor** (polish). Lead with blockers.
5. **Recommend.** For each finding, a concrete fix or a direction — not just "this is off".

## Senior rigor (always)

- **Specific, not vague:** "the CTA loses to the banner because both are saturated red" beats "hierarchy feels off".
- **Tied to goals:** reject taste-only notes; every issue costs the user or the goal something.
- **Balanced:** name what works and why, so it survives the next revision.
- **Prioritised:** the founder should know what to fix *first*.
- **Actionable:** each point lands with a fix or a clear next step.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Goal recap · First impression · Findings grouped Blocker / Major / Minor (each: observation · why · fix) · What's working · Top 3 to fix first. Show it in chat, iterate, then hand to `/post-comment`.
