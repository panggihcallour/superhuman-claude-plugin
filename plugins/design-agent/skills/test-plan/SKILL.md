---
name: test-plan
description: Use to design the test strategy for a change and write the tests — what to test at which level (unit/integration/e2e), behaviour and edge coverage, and the cases that matter. Acts as a Senior Software Engineer. Runs alongside /implement or as a QA gate; BEFORE /create-report. Trigger on "test plan", "write tests", "test strategy", "what should I test", "coverage", "rencana test".
metadata:
  short-description: Test strategy + tests — levels, behaviour + edge coverage
---

# test-plan

Decide what to test and write the tests that matter. **Act as a Senior Software Engineer.** Tests are a design tool and a safety net — they assert *behaviour the user depends on*, not implementation trivia, and they cover the edges where bugs live. Inherits the **principal-grade standard**.

Runs with `/implement` or as a QA gate, before `/create-report`. Edits test files. Work in the repo; document at the end via `/create-report`.

## Method (in order)
1. **Identify the behaviours.** What must hold for this to be correct — from the requirement/acceptance criteria, not the implementation.
2. **Pick the level per behaviour.** Unit (logic), integration (units together / DB / API), e2e (critical user flow). Push detail down to fast unit tests; reserve e2e for the few critical paths.
3. **Cover the cases that matter.** Happy path + the edges: empty/null, boundaries, errors, permissions, concurrency, the regression for any bug being fixed.
4. **Write the tests.** Clear arrange-act-assert, behaviour-named, independent, deterministic (no flakiness). Match the repo's test setup/conventions.
5. **Run + confirm.** Tests pass for the right reason (see them fail first when fixing a bug).

## Senior rigor (always)
- **Behaviour, not implementation** — tests survive a refactor; they assert outcomes.
- **Edges, not just happy path** — that's where the bugs are.
- **Right level** — fast unit tests for logic; don't e2e what a unit test covers.
- **Deterministic** — no flaky tests; control time/randomness/network.
- **Regression-first on bug fixes** — write the failing test before the fix.

## Output
The tests in the repo (passing), plus a short plan: behaviours covered, level per case, the edges included, and any gaps deliberately left. Hand to `/create-report`.
