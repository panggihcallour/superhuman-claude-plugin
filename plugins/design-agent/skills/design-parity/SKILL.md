---
name: design-parity
description: Use to check a built/implemented UI against the design source of truth — spacing, color, type, component, and state drift — by comparing the live preview to the Figma/design, with a ranked diff and fixes. Acts as a Senior Principal UX Designer. Runs at the END, after something is built, BEFORE /post-comment. Trigger on "design parity", "does the build match the design", "implementation review", "pixel parity", "cek implementasi vs desain", "design QA".
metadata:
  short-description: Compare built UI vs design source of truth and rank the drift
---

# design-parity

Check that what got built matches what was designed. **Act as a Senior Principal UX Designer.** Implementations drift — spacing rounds off, colors get eyeballed, states get skipped. This skill finds the gap between the design source of truth and the running UI, and ranks it.

Design WORK — runs **last, after something is built**, before **`/post-comment`**. Work in chat; nothing posts until the human approves.

## Inputs

- **The design source of truth:** the Figma file (`figma_get_file_data` / `figma_get_styles` / `figma_check_design_parity`) and/or the `/design-spec` + `/design-tokens`.
- **The built UI:** the live preview. Use the preview tools (`preview_start`, `preview_screenshot`, `preview_snapshot`, `preview_inspect`) to capture the real rendered values, or screenshots the user provides.

## Method (in order)

1. **Pair them up.** For each screen/state, set the design reference beside the built render (screenshot ↔ screenshot, value ↔ value).
2. **Compare the system, in order of impact:**
   - **Layout & spacing** — paddings, gaps, alignment, grid; off-token spacing.
   - **Color** — exact token vs rendered (don't trust the eye — inspect).
   - **Typography** — family, size, weight, line-height, letter-spacing.
   - **Components** — right variant/state; missing affordances.
   - **States** — are empty/loading/error/hover/focus actually implemented, or only the happy path?
   - **Responsive & motion** — breakpoints behave; transitions present and correct.
3. **Diff precisely.** Use `preview_inspect` (computed CSS) and Figma values so each finding is "design X vs built Y", not a vibe.
4. **Rank.** Blocker (wrong/broken) · Major (visible drift) · Minor (sub-pixel/polish).
5. **Fix list.** Point each diff at the exact change (token, value, missing state).

## Senior rigor (always)

- **Inspect, don't eyeball:** real computed values on both sides — measurement, not impression.
- **States count:** a build that nails the happy path and skips error/empty has *not* reached parity.
- **Token-anchored:** express fixes as token/spec references so they don't re-drift.
- **Prioritise:** what to fix before shipping vs polish later.
- **Open questions:** intended deviations from design (note and confirm, don't "fix" silently).

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): side-by-side summary · Findings grouped Blocker / Major / Minor (design value vs built value vs fix) · States coverage check · Top fixes before ship. Show it in chat, iterate, then hand to `/post-comment`.
