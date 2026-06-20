---
name: component-spec
description: Use to specify a reusable UI component — anatomy, variants, all states, sizes, props/config, content rules, accessibility, and usage do/don'ts — tool-agnostic (no framework binding). Acts as a Senior Principal UX Designer / design-systems lead. Can inspect components in Figma via the Figma MCP when connected. Runs AFTER /start-task (often after /design-tokens) and BEFORE /post-comment. Trigger on "component spec", "spec a component", "button states", "variants", "design a component", "spek komponen".
metadata:
  short-description: Tool-agnostic reusable-component spec (anatomy, variants, states, a11y)
---

# component-spec

Specify a single reusable component completely enough to build once and reuse everywhere. **Act as a Senior Principal UX Designer / design-systems lead.** A good spec removes ambiguity: anatomy, every variant and state, the rules for using it, and how it stays accessible. Keep it **tool-agnostic** — describe the component, don't bind it to a framework or library.

Design WORK — runs **between `/start-task`** and **`/post-comment`**, building on `/design-tokens`. Work in chat; nothing posts until the human approves.

## Inputs

- The brief + the token system (`/design-tokens`) so the spec references tokens, not raw values.
- **Figma MCP (optional):** if a file is connected, inspect an existing component with `figma_search_components` / `figma_get_component_details` / `figma_analyze_component_set` before specifying. Otherwise specify from scratch.

## Method (in order)

1. **Purpose & when to use.** What problem the component solves, and — critically — when *not* to reach for it (vs a neighbouring component).
2. **Anatomy.** The parts (container, label, icon, etc.), which are required vs optional, and the tokens that govern each (spacing, color, radius, type).
3. **Variants.** The dimensions of variation (e.g. hierarchy: primary/secondary/ghost; tone; size) and the valid combinations. Show the matrix; flag combinations that are *not* allowed.
4. **States.** Every interaction + system state: default, hover, focus(-visible), active, disabled, loading, error, selected, read-only. None optional — missing states are missing design.
5. **Behaviour & content rules.** Overflow/truncation, min/max width, label length, icon-only rules, responsive behaviour, what content is allowed inside.
6. **Accessibility.** Role/semantics, keyboard interaction + focus order, label/aria expectations, target size, contrast, motion/reduced-motion.
7. **Usage do / don't.** A few concrete, opinionated rules that prevent the misuse you can already predict.

## Senior rigor (always)

- **Tokens, not values:** every dimension cites a token from `/design-tokens`.
- **All states present:** focus and loading and error are first-class.
- **Composability:** note how it nests with / inside other components.
- **Predict misuse:** the do/don'ts target the mistakes people will actually make.
- **Open questions:** variants or behaviours needing a decision.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale) that *renders* the component's variants and states as live specimens, plus: Purpose · Anatomy (token-mapped) · Variant matrix · State table · Behaviour/content rules · Accessibility · Do/Don't · Open questions. Show it in chat, iterate, then hand to `/post-comment`.
