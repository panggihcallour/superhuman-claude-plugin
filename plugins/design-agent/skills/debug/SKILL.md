---
name: debug
description: Use to debug a bug or failure systematically — reproduce, isolate, find the root cause (not a symptom), fix minimally, and lock it with a regression test. Acts as a Senior Software Engineer. Runs on a reported bug/failure; BEFORE /create-report. Trigger on "debug", "fix the bug", "why is this failing", "root cause", "it's broken", "investigate the error", "cari bug".
metadata:
  short-description: Systematic debugging — reproduce, isolate, root-cause, fix, regression-test
---

# debug

Find the real cause, not a plausible one. **Act as a Senior Software Engineer.** Senior debugging is method, not guessing: reproduce it, isolate it, prove the root cause, then fix the cause (not the symptom) and lock it so it can't come back. Inherits the **principal-grade standard** — evidence over opinion.

Runs on a reported bug/failure, before `/create-report`. May edit files. Work in the repo; document at the end via `/create-report`.

## Method (in order)
1. **Reproduce.** Get a reliable, minimal reproduction. A bug you can't reproduce, you can't confirm you fixed. Note the exact conditions.
2. **Read the evidence.** The actual error/stack/logs — read them, don't skim. Form a hypothesis the evidence supports.
3. **Isolate.** Narrow it down — bisect, add targeted logging, check inputs at boundaries. Find the smallest failing case.
4. **Prove the root cause.** Identify *why* it happens, and confirm by predicting + observing. Don't stop at the symptom ("added a null check") — ask why it was null.
5. **Fix the cause, minimally.** The smallest change that addresses the root cause; don't smuggle in unrelated changes.
6. **Regression test.** Write a test that fails before the fix and passes after — so it can't silently return.
7. **Verify.** Repro is gone; existing tests still green.

## Senior rigor (always)
- **Reproduce first** — no fixing a bug you can't trigger.
- **Root cause, not symptom** — keep asking "why" until you hit the cause.
- **Evidence-driven** — hypotheses confirmed by observation, not vibes.
- **Locked with a test** — the regression test is part of the fix, not optional.
- **Minimal + in scope** — fix the bug; note other issues separately.

## Output
The fix in the repo + the regression test, plus a summary: the reproduction, the root cause (with evidence), the fix, and proof it's resolved. Hand to `/create-report`.
