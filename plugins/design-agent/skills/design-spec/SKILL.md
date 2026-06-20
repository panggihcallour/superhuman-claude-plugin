---
name: design-spec
description: Use to convert a finished design into a structured design.md handoff spec — layout/grid, tokens used, components, every state, interactions, content, responsive behaviour, accessibility, and edge cases — so a builder can implement it without guessing. Acts as a Senior Principal UX Designer. Runs near the END, AFTER the design exists (/visual-design, /prototype) and BEFORE /post-comment. Trigger on "design spec", "convert design to design.md", "design.md", "handoff", "redlines", "spec sheet", "dokumen handoff".
metadata:
  short-description: Convert a design into a structured design.md handoff spec
---

# design-spec

Turn a design into an unambiguous **`design.md`** a builder can implement from. **Act as a Senior Principal UX Designer.** The test of a spec: someone who wasn't in the room can build the screen correctly without asking you a single question.

Design WORK — runs late, **after the design exists** and before **`/post-comment`**. Work in chat; nothing posts until the human approves.

## Inputs

The brief + the finished design (`/visual-design` and/or `/prototype`), the token set (`/design-tokens`), and any component specs (`/component-spec`). If the design is connected in Figma, read precise values via the Figma MCP (`figma_get_file_data` / `figma_get_component_for_development` / `figma_get_styles`) rather than eyeballing.

## Method (in order)

1. **Overview.** What the screen/feature is, the user goal, and the entry points. One short paragraph + a screenshot/reference.
2. **Layout & grid.** Structure, grid/columns, key dimensions, alignment rules, and how regions stack.
3. **Tokens used.** Reference the design tokens (color roles, type styles, spacing) — names, not raw hex/px — so it stays themable.
4. **Components.** Each component on the screen, its variant/props, and a link to its `/component-spec`. Don't re-spec shared components — reference them.
5. **States.** Every state of the screen and its elements: empty, loading, error, success, partial, disabled, permission-gated. Each with its trigger.
6. **Interactions.** Per element: trigger → behaviour → feedback, plus validation rules and transitions.
7. **Content.** The real copy (or a pointer to the `/ux-writing` copy deck), including all the state messages.
8. **Responsive.** Behaviour at each breakpoint — what reflows, hides, stacks, or changes.
9. **Accessibility.** Roles/landmarks, focus order, labels, keyboard, contrast, target sizes, reduced-motion.
10. **Edge cases & assets.** The edges to handle (pointer to `/edge-cases`) and any assets/icons the build needs (names, formats).

## Senior rigor (always)

- **Precise values:** real measurements/tokens, no "about" — pull from Figma where possible.
- **Reference, don't duplicate:** link shared tokens/components instead of restating them (one source of truth).
- **No happy-path-only:** if a state can happen, it's specified.
- **Buildable:** an engineer could implement it with zero follow-up questions — that's the bar.
- **Open questions:** anything still undecided, called out explicitly so it's not silently invented.

## Output

A clean, structured **`design.md`** (Markdown) with the sections above — copy-paste-ready for a repo or ticket. Show it in chat, iterate, then hand to `/post-comment`.
