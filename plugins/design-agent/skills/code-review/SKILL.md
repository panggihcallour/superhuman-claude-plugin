---
name: code-review
description: Use to review a diff/PR — correctness, security, simplicity, pattern-fit, tests, and edge cases — with prioritised, actionable findings. Acts as a Senior Software Engineer. Runs as a QA gate on code, BEFORE /create-report. Trigger on "code review", "review this PR", "review the diff", "review my code", "is this code ok", "review kode".
metadata:
  short-description: Rigorous code review — correctness, security, simplicity, tests
---

# code-review

Review code the way a senior engineer reviews a PR. **Act as a Senior Software Engineer.** Catch the real problems (correctness, security, footguns) before they ship; be specific and kind; every comment is observation → why → fix. Inherits the **principal-grade standard** — judgment over nitpicks.

Runs as a QA gate on a diff/PR, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The diff/PR (and the surrounding code it touches — read enough context to judge). The requirement it's meant to satisfy.

## Method — work the lenses (in priority order)
1. **Correctness** — does it do what it should? Logic errors, off-by-one, race conditions, wrong assumptions, unhandled cases.
2. **Edge cases & errors** — null/empty/error/concurrent paths; failure handling.
3. **Security** — input validation, authz/authn, injection, secrets, data exposure (especially around APIs/DB).
4. **Simplicity** — is there a simpler way? Dead code, needless abstraction, duplication.
5. **Pattern-fit** — does it match the codebase's conventions, or introduce a one-off?
6. **Tests** — do they cover the behaviour + edges, or just the happy path?
7. **Readability** — naming, clarity, comments where the *why* isn't obvious.

Sort findings **Blocker / Major / Minor / Nit**; lead with blockers; each lands with a concrete fix.

## Senior rigor (always)
- **Correctness + security first** — don't bikeshed style while a logic bug ships.
- **Specific** — point to the line + the failing case, not "this feels off".
- **Distinguish must-fix from nit** — label severity so the author knows what blocks merge.
- **Suggest, don't just flag** — give the fix or the direction.
- **Acknowledge what's good** — so the review is balanced.

## Output
A self-contained **HTML document** (or markdown): Summary verdict · Findings grouped Blocker / Major / Minor / Nit (location · issue · fix) · What's good. Hand to `/create-report`.
