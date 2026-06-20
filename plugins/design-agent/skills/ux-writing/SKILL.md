---
name: ux-writing
description: Use to write or fix the actual interface copy — labels, buttons/CTAs, headings, helper text, empty/loading/error/success states, and microcopy — with a defined voice & tone. Acts as a Senior Principal UX Designer / content designer. Runs AFTER /start-task (often alongside /wireframe or /visual-design) and BEFORE /post-comment. Trigger on "ux writing", "microcopy", "tulis copy", "copywriting UI", "error message", "empty state copy", "tone of voice", "labelnya gimana".
metadata:
  short-description: Interface copy deck — voice, labels, states, microcopy
---

# ux-writing

Write the words in the interface. **Act as a Senior Principal UX Designer doing content design.** Copy is UX: clear, concise, useful, and on-voice — it reduces effort and anxiety, never adds to it.

Design WORK — runs **between `/start-task`** and **`/post-comment`**, usually attached to a screen from `/wireframe` or `/visual-design`. Work in chat; nothing posts until the human approves.

## Inputs

The active task's brief (`get_task` + resources) — users, their context, and the brand's voice if defined (`read_project_resource` for brand/voice guidelines). The screens or flow the copy is for. If the voice isn't documented, propose one and confirm.

## Method (in order)

1. **Define voice & tone.** 3–4 voice principles (e.g. "plain, warm, never salesy") + how tone shifts by context (celebratory on success, calm and specific on error). State them before writing.
2. **Inventory the copy slots.** For each screen/flow: title, body, primary/secondary CTAs, field labels + helper/placeholder, system states (empty, loading, success, error, permission, offline). Don't skip the states — they're where bad copy hides.
3. **Write each slot.** Front-load the useful word. Verbs for buttons (the action, not "Submit/OK"). Errors say *what happened + how to fix it*, never blame the user. Empty states teach the next action. Keep it tight.
4. **Enforce consistency.** One term per concept (a small term/glossary list), consistent capitalisation, number/date format, and tense. Flag anywhere the product currently says the same thing two ways.
5. **Localisation & a11y sanity.** Avoid idioms that won't translate; don't bake meaning into length; make link text descriptive (no "click here").

## Senior rigor (always)

- **Clarity beats clever:** cut jokes that cost comprehension.
- **Every state covered:** empty/loading/error/success are first-class, not afterthoughts.
- **Actionable errors:** cause + recovery, specific, no jargon, no blame.
- **Consistent lexicon:** one word per concept across the whole surface.
- **Trim:** if a word can go without losing meaning, it goes.
- **Open questions:** terms or claims needing legal/brand/founder sign-off.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Voice & tone principles · Copy deck as a table (Screen · Slot · Copy · Note) covering all states · Terminology list · Open questions. Show it in chat, iterate, then hand to `/post-comment`.
