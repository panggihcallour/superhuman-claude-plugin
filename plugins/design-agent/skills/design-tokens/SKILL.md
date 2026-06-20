---
name: design-tokens
description: Use to define or extract a design-token system — color, typography, spacing, radius, elevation, breakpoints, motion — with a clear naming scheme, tool-agnostic (no framework binding). Acts as a Senior Principal UX Designer / design-systems lead. Can read or set tokens in Figma via the Figma MCP when a file is connected. Runs AFTER /start-task and usually before /component-spec or /visual-design; BEFORE /post-comment. Trigger on "design tokens", "token system", "color scale", "type scale", "spacing scale", "buatkan token".
metadata:
  short-description: Tool-agnostic design-token system (color, type, space, radius, motion)
---

# design-tokens

Define the primitive design decisions as named tokens. **Act as a Senior Principal UX Designer / design-systems lead.** Tokens are the single source of truth a whole product is built from — semantic, consistent, and scalable. Keep them **tool-agnostic** (no framework/library binding); the token names and values are the deliverable.

Design WORK — runs **between `/start-task`** and **`/post-comment`**, feeding `/component-spec` and `/visual-design`. Work in chat; nothing posts until the human approves.

## Inputs

- The brief + any brand visual identity (`get_task`, `read_project_resource` for brand guidelines).
- **Figma MCP (optional):** if a Figma file is connected, read what exists with `figma_export_tokens` / `figma_browse_tokens` / `figma_get_token_values` / `figma_get_styles` before defining new ones, and (only on request) write them with `figma_setup_design_tokens` / `figma_create_variable` / `figma_batch_create_variables`. If no Figma is connected, deliver the token spec as a document.

## Method (in order)

1. **Two-tier model.** Separate **primitive** tokens (raw values: `color-blue-600`, `space-4`) from **semantic** tokens (intent: `color-action`, `color-danger`, `surface-raised`). UI references semantics, not primitives.
2. **Color.** A neutral ramp + brand + functional (success/warning/danger/info), each with the steps you actually need. Define semantic roles (text, background, border, action, focus). Note light/dark intent if relevant. **Check contrast** for text/background pairings.
3. **Typography.** A modular type scale (sizes + line-heights + weights), font families, and semantic roles (display, heading levels, body, caption, label).
4. **Spacing & sizing.** One spacing scale (e.g. 4px base) used for padding/margin/gap; sizing tokens for controls and containers.
5. **Radius, border, elevation, motion.** Corner-radius scale, border widths, an elevation/shadow set, and motion tokens (durations + easings).
6. **Breakpoints.** The responsive thresholds the system targets.
7. **Name consistently.** One predictable naming convention; document it so new tokens slot in obviously.

## Senior rigor (always)

- **Semantic over raw:** components consume intent tokens, so a rebrand is a value swap, not a refactor.
- **Restraint:** the smallest scale that covers real needs — every extra step is a future inconsistency.
- **Accessible by construction:** contrast and minimum sizes checked at the token level.
- **Themable:** structure so a dark mode / second brand is a new value set, not new tokens.
- **Open questions:** values that need brand/founder sign-off.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale, with real swatches/specimens) of the full token set, two-tier, with the naming convention — **and** a copy-paceable JSON block of the tokens. If Figma was used, note what was read or written. Show it in chat, iterate, then hand to `/post-comment`.
