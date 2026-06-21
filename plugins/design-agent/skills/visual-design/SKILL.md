---
name: visual-design
description: Use to take wireframes to a high-fidelity visual direction — type, color, spacing, imagery, depth, and components applied to the key screens — with the rationale behind each choice. Acts as a Senior Principal UX Designer. Runs AFTER /wireframe (and ideally after /design-tokens) and BEFORE /prototype or /figma-build; BEFORE /create-report. Trigger on "visual design", "hi-fi", "high fidelity", "make it look real", "apply the visual style", "desain visual", "polish the look".
metadata:
  short-description: Wireframe → high-fidelity visual direction for the key screens
---

# visual-design

Turn structure into a high-fidelity visual direction. **Act as a Senior Principal UX Designer.** Visual design is not decoration — it's hierarchy, focus, mood, and clarity made visible. Every choice (type, color, space, contrast, depth) earns its place by guiding the eye and the action.

Design WORK — runs **between `/wireframe`** and **`/prototype` / `/figma-build`**, then **`/create-report`**. Work in chat; nothing posts until the human approves.

## Inputs

The brief + the wireframes (`/wireframe`) + tokens (`/design-tokens`) + brand visual identity (`read_project_resource`). If there are no tokens yet, establish a minimal palette and type scale inline (and suggest running `/design-tokens` to formalise).

## Method (in order)

1. **Set the direction.** One or two lines on the intended feel and the principles guiding it (e.g. "calm, dense, trustworthy — restraint over flourish"). This is the bar every screen is judged against.
2. **Establish the system on screen.** Apply type scale, color roles, spacing rhythm, radius/elevation, and iconography consistently — tokens made concrete.
3. **Design the key screens** (the 2–4 that carry the experience). For each: real content (no lorem where it matters), clear visual hierarchy, deliberate focal point, and the primary action obvious at a glance.
4. **Show the important states** visually — not just the happy path: at least the empty and one "full/loaded" state for the core screen, and any state that changes the visual story.
5. **Annotate the rationale.** Why this hierarchy, why this emphasis, why this color does this job. Visual choices are arguments; make them.

## Senior rigor (always)

- **Hierarchy first:** squint — does the eye land where the task needs it?
- **Contrast & legibility:** real contrast ratios, real minimum sizes — accessible, not just pretty.
- **Consistency:** same token, same job, every screen; no one-off values.
- **Restraint:** remove before adding; every element justifies itself.
- **Real content:** design with realistic length, edge content, and data — not best-case mockups.
- **Open questions:** brand/art-direction calls needing sign-off.

## Output

A self-contained **HTML document** (inline CSS) rendering the key screens at high fidelity using the token system, with annotation callouts explaining the major choices, and the visual states. (For an editable Figma version, hand off to `/figma-build`.) Show it in chat, iterate, then hand to `/create-report`.
