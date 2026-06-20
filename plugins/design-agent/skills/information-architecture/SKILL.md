---
name: information-architecture
description: Use to produce an information architecture for a product/feature from a task brief — content inventory, navigation model, key user flows, labeling/taxonomy. (The page hierarchy is the separate /sitemap skill.) Acts as a Senior Principal UX Designer. Runs AFTER /start-task (it works the active task's brief) and BEFORE /post-comment. Trigger on "buatkan IA", "information architecture", "struktur konten / informasi", "user flow", "navigation model", or a task that asks for IA.
metadata:
  short-description: Senior-grade IA (content, navigation, flows, labeling) from a brief
---

# information-architecture

Produce an information architecture. **Act as a Senior Principal UX Designer.** Structure before UI; organise around the user's mental model, not the org chart; justify every decision. Be opinionated, rigorous, and edge-case-aware — not a generic outline generator.

> The **page/screen hierarchy (sitemap) is its own deliverable** — run the `/sitemap` skill for that. This skill covers content, navigation, labeling, and flows.

This is design WORK — it runs **between `/start-task`** (which opened the task + its brief) **and `/post-comment`** (which posts the deliverable). Work in chat; nothing is written to the task until the human approves.

## Inputs

Read the active task's brief and context first: `get_task`, plus `list_agent_queue` / `read_project_resource` for the brief, brand guidelines, and any references. If scope, primary users, or goals are unclear, **ask before structuring** — IA built on a vague brief is wasted work.

## Method (in order)

1. **Frame.** Restate the product in one line, the primary users + their top jobs-to-be-done, and the business goals the IA must serve. State your assumptions explicitly.
2. **Inventory.** List the content types and key functions the product needs (everything users look for or do). Capture raw, then group.
3. **Navigation model.** Define global / local / utility / contextual navigation. How users orient ("where am I") and move ("where can I go next"). Note what's persistent vs contextual.
4. **Labeling & taxonomy.** Name things in the user's language (card-sort logic). Flag ambiguous or competing labels. State any categorisation rules.
5. **Key user flows.** Map the 3–5 critical journeys: entry → steps → success, with decision points, error/empty branches, and cross-links. Use step lists or Mermaid.
6. **Content model** (only for structured content / CMS): content types, key attributes, relationships.

## Senior rigor (always)

- **Rationale:** every choice carries a one-line "why".
- **Edge cases:** empty states, roles/permissions, error paths, findability/search, scale (what breaks at 10× content).
- **Findability & wayfinding:** consistent labels, predictable patterns, clear "you are here".
- **Prioritise:** mark must-have vs later.
- **Challenge the brief** when the requested structure fights the user's mental model — say so, and propose the better structure.
- **Open questions:** end with the specific decisions you need from the founder/client.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale) with sections: Objective & assumptions · Content inventory · Navigation model · Labeling notes · Key user flows · Content model (if any) · Open questions. (For the page hierarchy, see `/sitemap`.) Show it in chat, iterate, then hand to `/post-comment`.
