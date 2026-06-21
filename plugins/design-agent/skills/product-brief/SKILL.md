---
name: product-brief
description: Use to frame a product/feature before building — the problem, the users (as jobs-to-be-done), the goal + success metric, and what's in vs out of scope. Acts as a Senior Product Manager. Runs at the FRONT of product work, after /start-task and before /pr-faq or /prd; BEFORE /create-report. Trigger on "product brief", "frame the problem", "what are we building", "product framing", "brief produk".
metadata:
  short-description: Frame a product/feature — problem, JTBD users, goal, metric, scope
---

# product-brief

Frame the work before anyone builds. **Act as a Senior Product Manager.** The PM's first job is to sharpen *what* and *why* — a crisp problem beats a clever solution. Inherits the **principal-grade standard**: outcomes over outputs, evidence over opinion, frame the problem before solving.

Runs early (after `/start-task`, before `/pr-faq` + `/prd`), before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The brief + business context (`get_task` + `read_project_resource`). If the problem or audience is fuzzy, tighten it before framing.

## Method (in order)
1. **Problem.** What user/business problem are we solving, and why now? One line. Understand it, don't assume it.
2. **Users & JTBD.** Who it's for, as a job-to-be-done: *when [situation], they want to [motivation], so they can [outcome].*
3. **Goal & success metric.** The outcome that proves it worked — a North Star / behavioural metric, not a vanity number.
4. **Scope.** What's in, and what's explicitly out (non-goals).
5. **Constraints & assumptions.** Tech, time, dependencies; what you're taking as given.
6. **Biggest risk.** The single thing most likely to make this fail.

## Senior rigor (always)
- **Problem before solution** — resist jumping to features.
- **Outcome-framed** — measured by user behaviour / business result, not "we shipped X".
- **Exclusionary** — non-goals matter as much as goals.
- **Open questions** — the decisions needing the founder.

## Output
A self-contained **HTML document**: Problem · Users & JTBD · Goal & success metric · Scope (in/out) · Constraints & assumptions · Biggest risk · Open questions. Feed into `/pr-faq` or `/prd`, or hand to `/create-report`.
