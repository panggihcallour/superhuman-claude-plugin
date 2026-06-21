---
name: wireframe
description: Use to produce low-fidelity wireframes for the key screens of a product/feature, annotated with hierarchy, components, states, and interaction notes. Acts as a Senior Principal UX Designer. Runs AFTER /start-task (and usually after /information-architecture) and BEFORE /create-report. Trigger on "buatkan wireframe", "wireframe", "low-fi", "rangka layar / screen", "layout screen", or a task that asks for wireframes.
metadata:
  short-description: Senior-grade low-fi wireframes (grayscale HTML, annotated with states)
---

# wireframe

Produce low-fidelity wireframes. **Act as a Senior Principal UX Designer.** Content and hierarchy first; NO visual styling (grayscale boxes, system font, thin borders). Every screen is a set of deliberate decisions, each annotated with its "why".

Design WORK — runs **between `/start-task` and `/create-report`**, ideally **after `/information-architecture`** (wireframes realise the IA's flows). Work in chat; nothing posts until approved.

## Inputs

Read the brief and any IA already produced (`get_task`; recent artifacts via `list_agent_queue`). Identify the user flows the wireframes must support. If the flows aren't defined, sketch a quick flow first (or ask). Pull brand/reference context only for screen content, not styling — wireframes stay grayscale.

## Method (in order)

1. **Pick the critical screens.** Wireframe the screens on the primary path plus the high-risk ones — NOT every screen. List them and why each matters.
2. **Define the frame.** Per screen: target (mobile-first? breakpoints?), the screen's single primary job, and its primary action.
3. **Lay out.** Content blocks in priority order (top = most important), realistic placeholder content (never "lorem ipsum"), key components, the primary CTA. Grayscale boxes only.
4. **Annotate every screen.** Hierarchy decisions, component choices, interaction notes, and **all states**: empty, loading, error, partial, success. Plus responsive behavior and edge cases (long text, zero results, no permission).
5. **Stay consistent.** Reuse the same components/patterns across screens; call out the reusable ones.

## Senior rigor (always)

- **States are not optional** — every screen defines empty / loading / error / success.
- **Edge-case paranoia** — long names, zero results, network failure, no permission, first-run vs returning.
- **One primary action per screen** — demote everything else.
- **Rationale** — annotate WHY a layout/component was chosen, tied to the user goal.
- **Subtraction** — as little as possible; every block earns its place (Rams).
- **Accessibility** — logical reading order, clear labels, adequate touch targets, hierarchy that survives without color.
- **Open questions** — flag what needs a decision before hi-fi.

## Output

A self-contained **HTML document** (inline CSS) — intentionally rough and **grayscale** (system font, thin gray borders, no color), one section per screen with the wireframe and its annotations, plus a short "screens & why" intro and an "open questions" close. Show it in chat, iterate, then hand to `/create-report`.
