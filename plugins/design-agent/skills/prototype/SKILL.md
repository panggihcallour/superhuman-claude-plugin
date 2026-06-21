---
name: prototype
description: Use to define an interactive prototype of a flow — screen-to-screen navigation, transitions, interaction and gesture details, and state changes — so the experience can be felt, not just seen. Acts as a Senior Principal UX Designer. Runs AFTER /wireframe or /visual-design and BEFORE /create-report. Trigger on "prototype", "make it interactive", "clickable", "interaction design", "prototipe", "flow interaktif", "transitions".
metadata:
  short-description: Interactive prototype of a flow — navigation, interactions, transitions, states
---

# prototype

Make the design something you can move through. **Act as a Senior Principal UX Designer.** A prototype tests the *experience over time* — flow, feedback, transitions, and how state changes feel — which static screens can't show.

Design WORK — runs **between `/wireframe` / `/visual-design`** and **`/create-report`**. Work in chat; nothing posts until the human approves.

## Inputs

The brief + the screens from `/wireframe` or `/visual-design`, and the key user flow being prototyped (one journey at a time). If the target flow isn't obvious, confirm which one matters most.

## Method (in order)

1. **Pick the flow + fidelity.** One primary journey (entry → success). Decide lo-fi (wireframe-level, for flow validation) or hi-fi (styled, for feel).
2. **Map the screen graph.** Each screen/state node and every transition between them — including the branches: error, empty, loading, back/cancel, and decision forks.
3. **Specify the interactions.** For each interactive element: trigger (tap/hover/drag/keyboard), the response, and the feedback (what the user sees/feels confirming it worked).
4. **Specify the motion.** Transitions between screens and state changes: type, direction, duration, easing — and *why* (motion should explain the change, not decorate it). Respect reduced-motion.
5. **Cover state over time.** Loading → loaded, optimistic updates, success/failure feedback, and how the system communicates progress and recovery.
6. **Build it.** Produce a clickable HTML prototype of the flow where feasible (linked screens + the key interactions/transitions); otherwise a precise interaction spec that a builder or `/figma-build` can execute.

## Senior rigor (always)

- **Feedback always:** no action without a visible response; no dead ends.
- **Branches, not just the happy path:** error/empty/loading are part of the prototype.
- **Motion with meaning:** every transition explains a change; honour reduced-motion.
- **Realistic timing:** show latency states, don't pretend everything is instant.
- **Open questions:** interactions needing a technical-feasibility or product call.

## Output

A clickable **HTML prototype** of the flow (self-contained, inline CSS/JS) where feasible, **plus** a short interaction + motion spec (screen graph, triggers/responses, transitions). Show it in chat, iterate, then hand to `/create-report`.
