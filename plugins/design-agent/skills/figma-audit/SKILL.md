---
name: figma-audit
description: Use to audit a Figma file's hygiene via the Figma MCP — auto-layout usage, layer naming, and design-system adherence (detached instances, off-token colors/type, ad-hoc values) — with a fix list. Acts as a Senior Principal UX Designer / design-systems lead. Runs as a QA gate on Figma work, BEFORE /create-report. Trigger on "figma audit", "check auto layout", "check layer naming", "is this using the design system", "audit figma", "cek figma", "design system compliance".
metadata:
  short-description: Figma hygiene audit — auto layout, layer naming, design-system adherence
---

# figma-audit

Audit a Figma file for craft and system hygiene. **Act as a Senior Principal UX Designer / design-systems lead.** Three things in one pass: is it built on **auto layout**, are **layers named** like a teammate could navigate them, and does it actually **use the design system** (components, styles, tokens) instead of detached one-offs.

Design WORK — a QA gate on Figma work, before **`/create-report`**. Requires the Figma MCP; if it isn't connected, say so. Work in chat; nothing posts until the human approves.

## Inputs

The Figma file under review. Start with `figma_get_status` / `figma_list_open_files`, then drive the audit with `figma_audit_design_system`, `figma_lint_design`, `figma_get_file_data`, `figma_get_styles`, and component inspection tools. Re-`figma_search_components` for fresh node IDs.

## Method (in order)

1. **Auto layout.** Find frames/components built with absolute positioning where auto layout belongs; flag "hug" where "fill" is needed (lopsided/non-responsive layouts), inconsistent padding/gap, and stacks that won't reflow.
2. **Layer naming.** Flag default names ("Frame 12", "Group 34", "Rectangle 5"), inconsistent casing, and structure that's unnavigable. Propose a naming convention and the renames.
3. **Design-system adherence.** Run `figma_audit_design_system` / `figma_lint_design`: detached instances that should be components, raw colors/text off the token/style set, off-scale spacing/radius, and components that drifted from the library.
4. **Quantify.** A small scorecard (e.g. % auto-layout, # unnamed layers, # detached instances, # off-token values) so progress is measurable.
5. **Fix list.** Concrete, prioritised remediations — and offer to apply the safe, mechanical ones (renames, re-link to components) via the MCP on request.

## Senior rigor (always)

- **Tool-grounded:** findings come from the MCP audit/lint output + inspection, not assumption.
- **Prioritise:** detached components and broken auto layout before cosmetic naming.
- **Actionable:** name the node, the problem, and the fix; offer to apply the mechanical ones.
- **Convention, not nitpick:** propose the naming/structure rule, then list violations against it.
- **Open questions:** intentional deviations to confirm before "fixing".

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Scorecard · Auto-layout findings · Layer-naming findings · Design-system adherence findings · Prioritised fix list (with which are auto-applicable). Show it in chat, iterate, then hand to `/create-report`.
