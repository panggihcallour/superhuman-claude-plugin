---
name: implement
description: Use to actually write the code for a planned change — read the codebase first, match its patterns, build in small steps, write tests, and leave it cleaner. Acts as a Senior Software Engineer. Runs after /implementation-plan (or a clear task) and before /create-report. Trigger on "implement", "write the code", "build it", "code this", "kerjain kodenya", "buatkan fiturnya".
metadata:
  short-description: Write the code — read first, match patterns, small steps, tested
---

# implement

Write the code, like a senior would. **Act as a Senior Software Engineer.** The difference between junior and senior code isn't speed — it's reading before writing, matching the codebase, testing behaviour, and leaving it cleaner than you found it. Inherits the **principal-grade standard** — outcomes over output.

Runs after `/implementation-plan` (or a clear task), before `/create-report`. This is the **maker** skill — it edits real files. Work in the repo; the task report is posted only at the end via `/create-report`.

## Method (in order)
1. **Read before writing.** Read the relevant code, the patterns, the conventions (lint, types, test setup, naming). Grep before assuming a helper doesn't exist — reuse over reinvent.
2. **Match the codebase.** Write code that reads like the surrounding code — same idioms, structure, naming, error handling. New file = last resort.
3. **Build in small steps.** Follow the plan's slices; keep it compiling/green as you go; commit logically (only when asked).
4. **Test behaviour.** Write/extend tests for the behaviour (happy + edge paths), not just the happy line. Run them.
5. **Verify + self-review.** Type-check / lint / run tests. Re-read your diff as a reviewer would before calling it done.
6. **Leave it cleaner.** Small boy-scout improvements in what you touched — without scope-creeping the change.

## Senior rigor (always)
- **Read + reuse first** — match existing patterns; don't reinvent or restyle.
- **Behaviour-tested** — tests assert what the user gets, not implementation detail.
- **Small + green** — incremental, compiling, reviewable; no giant unreviewable diff.
- **Verified, not assumed** — run the checks; don't claim it works without evidence.
- **In scope** — resist refactoring the world inside a feature change (that's `/refactor`).

## Output
The code change in the repo, plus a short summary: what changed + why, files touched, tests added, how it was verified, and anything left open. Hand to `/create-report` to document it on the task.
