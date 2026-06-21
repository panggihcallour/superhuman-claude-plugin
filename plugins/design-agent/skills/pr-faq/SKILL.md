---
name: pr-faq
description: Use to write an Amazon-style working-backwards PR-FAQ — a mock internal press release plus FAQ, written from the customer and the end state, before building anything. Acts as a Senior Product Manager. Runs early in product work (after /product-brief) and before /prd; BEFORE /create-report. Trigger on "pr-faq", "press release", "working backwards", "prfaq", "future press release".
metadata:
  short-description: Amazon working-backwards PR-FAQ — press release + FAQ, customer-first
---

# pr-faq

Work backwards from the launch. **Act as a Senior Product Manager.** Amazon's PR-FAQ forces clarity *before* building: if you can't write a compelling press release for the customer, the idea isn't ready. Inherits the **principal-grade standard** — start from the customer outcome, be honest about the hard questions.

Runs after `/product-brief`, before `/prd`, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The product brief (`/product-brief`) — problem, users, outcome. If there's no brief, frame the problem first.

## Method (in order)
1. **Press release (the PR).** A short mock internal release dated at launch: headline, sub-head, the customer problem, the solution in plain language, a customer quote, how to get started. Written for the **customer**, jargon-free.
2. **Customer FAQ.** The questions a customer would ask — what it does, how it helps, what it costs, how it's different.
3. **Internal/stakeholder FAQ.** The hard questions the team must answer: why now, why us, the biggest risks, what we're NOT doing, how we'll measure success, what could make this fail. **Don't dodge the uncomfortable ones — that's the point.**

## Senior rigor (always)
- **Customer-first language** — if it needs jargon to sound good, it isn't ready.
- **Answer the hard questions** — the internal FAQ is where weak ideas break; surface the risks.
- **Concrete** — a real headline + real numbers, not "revolutionary platform".
- **Outcome over feature** — the press release sells the customer benefit, not the build.
- **Open questions** — assumptions that must be validated.

## Output
A self-contained **HTML document**: the Press Release · Customer FAQ · Internal/stakeholder FAQ · Open questions. Feed into `/prd` + `/product-discovery`, or hand to `/create-report`.
