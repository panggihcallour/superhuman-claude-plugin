---
name: brand-identity
description: Use to build the full visual identity system from the logo and art direction — color palette, typography, logo system, imagery/illustration style, graphic motifs, and grid — as one coherent, reusable system. Acts as a Senior Brand & Graphic Designer / design-systems lead. Runs after /logo-design (and /moodboard) and before /marketing-assets or /brand-guidelines; BEFORE /post-comment. Trigger on "brand identity", "identity system", "visual identity", "brand system", "identitas brand".
metadata:
  short-description: Full visual identity system — color, type, logo system, imagery, motifs
---

# brand-identity

Turn a logo + direction into a complete, reusable identity system. **Act as a Senior Brand & Graphic Designer / design-systems lead.** A brand isn't a logo — it's a system that stays recognisable across every touchpoint while flexing to each.

Design WORK — runs after `/logo-design` + `/moodboard`, before `/marketing-assets` + `/brand-guidelines`, before `/post-comment`. Inherits the **principal-grade standard**. Can read/set styles in Figma via the Figma MCP. Work in chat; nothing posts until approved.

## Inputs

The logo (`/logo-design`), art direction (`/moodboard`), and strategy (`/brand-strategy`). Build the system to express all three consistently.

## Method (in order)

1. **Color.** A purposeful palette — primary, secondary, neutrals, functional accents — with roles (where each is used), real values, and **contrast checked** for legible pairings (accessibility, not just aesthetics).
2. **Typography.** A type system: display/heading/body/caption families (1–2 typefaces), a clear scale + hierarchy, weights, and pairing rationale.
3. **Logo system.** How the logo behaves in the identity: lockups, clear space, sizing, color treatments, placement.
4. **Imagery & illustration.** The photography/illustration style + art-direction rules that make any image feel on-brand.
5. **Graphic motifs & layout.** Signature elements (shapes, patterns, lines, iconography style) + a layout grid that ties applications together.
6. **Show it applied.** Render the system on 2–3 sample touchpoints so it reads as a system, not a parts list.

## Senior rigor (always)

- **Systematic, not decorative:** every element has a role + usage rule; a rebrand is a value swap, not a redraw.
- **Recognisable + flexible:** consistent enough to recognise, flexible enough to apply everywhere.
- **Accessible by construction:** color contrast + type sizes checked at the system level.
- **Restraint:** the smallest set that covers real needs.
- **Open questions:** system calls needing sign-off.

## Output

A self-contained **HTML document** (inline CSS, real swatches/specimens) of the full system — color (roles + values), type (scale + specimens), logo system, imagery rules, motifs + grid — plus the applied samples, **and** a copy-pasteable token/JSON block of the core values. Show it in chat, iterate, then feed into `/marketing-assets` + `/brand-guidelines`, or hand to `/post-comment`.
