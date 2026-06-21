---
name: prd
description: Use to write the product requirements doc/spec — problem, solution, user stories with acceptance criteria, scope and non-goals, success metrics, and open questions — so design and engineering can build without guessing. Acts as a Senior Product Manager. Runs after discovery (/product-brief, /product-discovery) and BEFORE /create-report. Trigger on "prd", "product spec", "requirements", "user stories", "acceptance criteria", "spec produk".
metadata:
  short-description: Product requirements doc — stories, acceptance criteria, scope, metrics
---

# prd

Specify what to build clearly enough that the team doesn't have to guess. **Act as a Senior Product Manager.** A PRD defines the *what* and *why* (and the bar for done) — it leaves the *how* to design and engineering. Inherits the **principal-grade standard** — outcome-framed, scope-disciplined.

Runs after `/product-brief` + `/product-discovery`, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The brief, PR-FAQ, and discovery findings. Reference them rather than restating.

## Method (in order)
1. **Problem & context.** The user problem, why now, who it's for (JTBD) — short.
2. **Goal & success metrics.** The outcome + how it's measured (North Star + supporting), and guardrail metrics (what must NOT get worse).
3. **Solution overview.** The approach in plain language — what the product does, not how it's coded.
4. **User stories + acceptance criteria.** Per story: *As a [user], I want [capability], so that [outcome]* — with **acceptance criteria** (Given/When/Then) that define "done". This is the core of the doc.
5. **Scope & non-goals.** Explicitly in, explicitly out, and what's deferred to later.
6. **Edge cases & dependencies.** The states/edges to handle (pointer to design `/edge-cases`), and external dependencies.
7. **Open questions.** Decisions still needed, with owners.

## Senior rigor (always)
- **Acceptance criteria are testable** — "done" is unambiguous, not "works well".
- **What, not how** — don't prescribe the UI or the implementation; that's design/eng.
- **Non-goals explicit** — scope creep dies here.
- **Outcome-tied** — every story ladders to the goal metric.
- **Open questions** — surfaced, not silently assumed.

## Output
A self-contained **HTML document** (or markdown): Problem & context · Goal & metrics · Solution overview · User stories + acceptance criteria · Scope & non-goals · Edge cases & dependencies · Open questions. Hand to `/create-report` (or feed design/eng).
