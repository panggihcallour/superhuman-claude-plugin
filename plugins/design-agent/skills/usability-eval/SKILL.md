---
name: usability-eval
description: Use to evaluate usability — either plan/run a task-based usability test, or run a heuristic evaluation against Nielsen's 10 heuristics (expert review, no users) — and report severity-ranked issues. Acts as a Senior UX & Market Researcher. Runs on a design/build; BEFORE /create-report. Trigger on "usability test", "usability evaluation", "heuristic evaluation", "expert review", "find usability issues", "uji usability".
metadata:
  short-description: Usability test plan OR heuristic evaluation (Nielsen's 10), ranked issues
---

# usability-eval

Find where the interface trips people up. **Act as a Senior UX & Market Researcher.** Two tools for two budgets: a **usability test** (behavioral — watch real users attempt tasks) when you can recruit, or a **heuristic evaluation** (expert review against Nielsen's 10) to find likely issues cheaply when you can't. Inherits the **principal-grade standard** — judgment, not a checklist.

Runs on a design/build, before `/create-report`. Work in chat; nothing posts until approved.

## Pick the mode
- **Usability test** — you can recruit users; you need real behavioural evidence on specific tasks.
- **Heuristic evaluation** — fast, no users; budget-stretching expert review to surface likely problems.

## Usability test
1. **Tasks.** Realistic, goal-based tasks (not "click the button") that exercise the key flows.
2. **Protocol.** Think-aloud, success/failure + time + where they struggle, non-leading facilitation, 5+ participants for qualitative depth.
3. **Capture.** What they did, where they hesitated/failed, quotes — behaviour first.
4. **Report.** Issues by severity, each tied to the observed task failure.

## Heuristic evaluation
1. **Evaluate against Nielsen's 10** (as judgment, not a checklist): visibility of system status · match to the real world · user control & freedom · consistency & standards · error prevention · recognition over recall · flexibility & efficiency · aesthetic & minimalist design · help users recover from errors · help & documentation.
2. **For each issue:** the heuristic violated, where, and the severity (cosmetic → catastrophic).
3. **Note** it's expert-predicted, not user-observed — validate the big ones with a test.

## Senior rigor (always)
- **Right method for the budget** — test for evidence, heuristics for speed; say which and why.
- **Severity-ranked** — not all issues are equal; lead with the blockers.
- **Behaviour over opinion** (test) / **judgment over checklist** (heuristics).
- **Actionable** — each issue lands with a fix or direction.
- **Open questions** — what needs a test to confirm.

## Output
A self-contained **HTML document**: Mode + rationale · (Test: tasks · protocol · findings) or (Heuristic: issues by heuristic) · Issues ranked by severity (location · issue · fix) · What to validate next. Hand to `/create-report`.
