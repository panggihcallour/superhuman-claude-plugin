---
name: graphic-critique
description: Use to critique brand/graphic work rigorously — concept, composition/layout, typography, color, craft, and brand consistency — with prioritised, actionable fixes, not taste. Acts as a Senior Brand & Graphic Designer. Runs as a QA gate after graphic work exists, BEFORE /create-report. Trigger on "graphic critique", "critique this design", "review the logo", "feedback on the brand", "kritik desain grafis", "review visual".
metadata:
  short-description: Rigorous brand/graphic critique — concept, composition, type, color, consistency
---

# graphic-critique

Critique graphic work the way a senior art director would in a crit. **Act as a Senior Brand & Graphic Designer.** Direct and specific — every point is observation → why it matters → fix, judged against the concept and the brand, not personal taste.

Design WORK — a QA gate after graphic work exists, before `/create-report`. Inherits the **principal-grade standard**. Work in chat; nothing posts until approved.

## Inputs

The brand strategy/concept it should express (`/brand-strategy`) and the work itself (HTML/SVG in chat, or a Figma file — use the Figma MCP to see it precisely). You critique against the concept + brand, so anchor on those first.

## Method (in order)

1. **Restate the concept + brand.** What the work should express (personality, message) — the yardstick.
2. **First impression (squint test).** What reads first? Does it feel on-brand and on-concept in 3 seconds? Note the gut read before analysing.
3. **Work the lenses:**
   - **Concept** — does the work express a clear idea, or is it just styled?
   - **Composition & layout** — grid, balance, hierarchy, whitespace, alignment, focal point.
   - **Typography** — pairing, hierarchy, scale, kerning/leading/measure, legibility.
   - **Color** — harmony, contrast, accessibility, brand fidelity.
   - **Craft** — detailing, consistency, finish, optical adjustments.
   - **Brand consistency** — does it hold to `/brand-identity`, or drift off-system?
4. **Prioritise.** Sort findings **Blocker / Major / Minor**; lead with blockers.
5. **Recommend.** Each finding lands with a concrete fix or direction.

## Senior rigor (always)

- **Concept-anchored:** the weakest critique is "I'd change the color"; the strongest is "the mark doesn't carry the concept because…".
- **Specific, not taste:** tie every issue to the concept, the brand, or a craft principle.
- **Balanced:** name what works + why so it survives the revision.
- **Prioritised + actionable:** the founder knows what to fix first, and how.

## Output

A self-contained **HTML document** (inline CSS, grayscale): Concept/brand recap · First impression · Findings grouped Blocker / Major / Minor (observation · why · fix) · What's working · Top 3 to fix first. Show it in chat, iterate, then hand to `/create-report`.
