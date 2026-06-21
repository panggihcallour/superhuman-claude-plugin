<!-- TEMPLATE for /design-spec — copy this, fill every [bracket], delete comments + unused sections.
Reference tokens + components by name (don't restate them). The test: a builder ships it with zero follow-up questions. -->

# design.md — [Screen / feature]

> Design Agent · Senior Principal UX Designer · [date] · source: [Figma link / visual-design]

## Overview
[What this screen/feature is, the user goal, the entry points. One short paragraph + a screenshot/reference.]

## Layout & grid
- Structure: [regions, how they stack]
- Grid / columns: [e.g. 12-col, gutter, margins]
- Key dimensions: [container max-width, key spacings — as tokens]

## Tokens used
[Reference design tokens by name, not raw values — keeps it themable.]
- Color: `color-…`, `color-…`
- Type: `text-heading`, `text-body`, …
- Spacing: `space-…`

## Components
[Each component on the screen + its variant/props + link to its /component-spec. Don't re-spec shared components.]
- `[Component]` — variant: `[…]` → see component-spec

## States
[Every state + its trigger — none skipped.]
| State | Trigger | Behaviour |
|---|---|---|
| empty / loading / error / success / partial / permission-gated | [trigger] | [what shows] |

## Interactions
[Per element: trigger → behaviour → feedback, + validation + transitions.]

## Content
[The real copy (or pointer to the /ux-writing copy deck), including all state messages.]

## Responsive
[Behaviour per breakpoint — what reflows, hides, stacks, changes.]

## Accessibility
[Roles/landmarks · focus order · labels · keyboard · contrast · target sizes · reduced-motion.]

## Edge cases & assets
- Edges to handle: [pointer to /edge-cases]
- Assets/icons the build needs: [names, formats]

## Open questions
- [Anything still undecided — don't let the build silently invent it.]
