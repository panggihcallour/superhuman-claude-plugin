---
name: moodboard
description: Use to set the visual art direction for a brand or campaign — aesthetic, references, color/type/imagery mood, and do/don't — before producing final assets. Acts as a Senior Brand & Graphic Designer / art director. Runs after /brand-strategy and before /logo-design or /brand-identity; BEFORE /create-report. Trigger on "moodboard", "art direction", "visual direction", "look and feel", "aesthetic", "referensi visual", "mood".
metadata:
  short-description: Art direction — aesthetic, references, color/type/imagery mood, do/don't
---

# moodboard

Set the visual direction before committing to final design. **Act as a Senior Brand & Graphic Designer / art director.** Art direction is a deliberate argument for a feeling — not a reference dump. Every reference earns its place by expressing the strategy.

Design WORK — runs after `/brand-strategy`, before `/logo-design` + `/brand-identity`, before `/create-report`. Inherits the **principal-grade standard**. Work in chat; nothing posts until approved.

## Inputs

The brand strategy (`/brand-strategy`) — personality, archetype, audience. Any references/guidelines from the project (`read_project_resource`). If no strategy exists, establish the intended feeling first.

## Method (in order)

1. **Translate strategy → feeling.** One or two lines: the mood the visuals must evoke (e.g. "warm, crafted, confident — not corporate"), traced to the personality/archetype.
2. **Direction options (1–3).** Where the brief allows, offer distinct aesthetic directions (e.g. "editorial minimal" vs "bold maximal") so there's a real choice — each with its rationale.
3. **Aesthetic pillars.** For the chosen/each direction: color mood, typographic mood, imagery/photography/illustration style, texture/finish, composition feel, motion feel (if relevant).
4. **References with reasons.** Curated references — rendered as swatches/specimens or described precisely — each annotated with *why* it fits, not just "looks nice".
5. **Do / don't.** Concrete guardrails: the looks to chase and the looks to avoid (e.g. "no drop shadows, no stocky photography").

## Senior rigor (always)

- **Intentional, not a collage:** every element expresses the strategy; cut the merely pretty.
- **Differentiated:** the direction shouldn't look like the competitors named in `/brand-strategy`.
- **Decisive:** if offering options, end with a recommendation + why.
- **Feasible:** the direction must be producible with the team/budget.
- **Open questions:** art-direction calls needing sign-off.

## Output

**Start from the scaffold in `references/template.html`** — copy it and fill in every placeholder (keep the house style). It produces a self-contained **HTML document** (inline CSS) rendering the direction(s) as a real moodboard — color swatches, type specimens, imagery/texture notes, composition examples — with rationale + do/don't. Show it in chat, iterate, then feed into `/logo-design` + `/brand-identity`, or hand to `/create-report`.
