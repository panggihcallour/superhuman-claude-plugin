---
name: sitemap
description: Use to produce a sitemap — the structural page/screen hierarchy of a product or feature (sections, nesting, primary vs secondary), organised around the user's mental model. Acts as a Senior Principal UX Designer. Runs AFTER /start-task (usually alongside /information-architecture) and BEFORE /post-comment. Trigger on "buatkan sitemap", "sitemap", "struktur halaman", "page hierarchy", "site structure", "peta halaman".
metadata:
  short-description: Senior-grade sitemap — page/screen hierarchy as an annotated tree
---

# sitemap

Produce a sitemap — the **structural hierarchy** of the product's pages/screens. **Act as a Senior Principal UX Designer.** Organise by the user's mental model (not the org chart); prefer broad-and-shallow; every grouping carries a reason.

This is design WORK — it runs **between `/start-task`** and **`/post-comment`**. It pairs with `/information-architecture`: IA handles content, navigation, labeling, and flows; the **page hierarchy lives here.** Work in chat; nothing posts until the human approves.

## Inputs

Read the brief and any content inventory already produced: `get_task`, plus `list_agent_queue` / `read_project_resource` for the brief and references. If the page/feature scope is unclear, **ask before structuring**.

## Method (in order)

1. **List the pages/screens** the product needs — pull from the brief and (if present) the IA content inventory. Capture raw first.
2. **Group** them into sections by the users' mental model — how users expect to find things, not the internal org structure.
3. **Nest** into levels. Prefer broad-and-shallow (minimise clicks-to-reach); flag any branch deeper than three levels and justify it.
4. **Classify** each node: **primary** (main nav) · **secondary** · **utility** (login, settings, legal) · **contextual** (only reached from within a flow).
5. **Label** in the user's language; flag ambiguous or competing labels.
6. **Render** as an indented tree, with a one-line rationale on the non-obvious groupings.

## Senior rigor (always)

- **Rationale** for every grouping / nesting decision — a one-line "why".
- **Depth discipline** — broad-and-shallow; call out and justify deep branches.
- **Edge pages** — empty/zero states, error pages, auth-gated, role-specific, search, 404.
- **Scale** — does the structure still hold at 10× the pages?
- **Primary path first** — pages on the main user journey are top-level or one click away.
- **Open questions** — flag the structural decisions you still need confirmed.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale) showing the sitemap as an indented / visual **tree**, each node tagged (primary / secondary / utility / contextual), with rationale notes and an open-questions close. Show it in chat, iterate, then hand to `/post-comment`.
