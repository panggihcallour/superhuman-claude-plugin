---
name: refactor
description: Use to improve the structure of existing code without changing its behaviour — reduce complexity/duplication, clarify, and keep tests green. Acts as a Senior Software Engineer. Runs on existing code; BEFORE /create-report. Trigger on "refactor", "clean up the code", "reduce complexity", "simplify this code", "tidy up", "rapikan kode".
metadata:
  short-description: Behaviour-preserving refactor — reduce complexity, keep tests green
---

# refactor

Improve the code without changing what it does. **Act as a Senior Software Engineer.** Refactoring is disciplined: behaviour-preserving, test-backed, in small steps — not a rewrite in disguise. Inherits the **principal-grade standard** — outcomes (maintainability) over churn.

Runs on existing code, before `/create-report`. Edits real files. Work in the repo; document at the end via `/create-report`.

## Method (in order)
1. **Pin behaviour with tests first.** Ensure tests cover the current behaviour before changing anything — they're the safety net. Add characterization tests if coverage is thin.
2. **Name the smell.** What's actually wrong — duplication, long function, unclear naming, leaky abstraction, deep nesting — and why it costs.
3. **Small, safe steps.** One behaviour-preserving transformation at a time; run tests after each; keep it green throughout.
4. **Don't change behaviour.** No new features, no bug "fixes" smuggled in — if you find a bug, note it separately.
5. **Verify equivalence.** Tests still green; the diff is structure-only.

## Senior rigor (always)
- **Tests first** — never refactor code you can't verify is unchanged.
- **Behaviour-preserving** — same inputs → same outputs; scope is structure only.
- **Small steps** — many tiny safe changes, not one big risky one.
- **Justified** — every change reduces real complexity; don't churn for taste.
- **Bugs noted, not fixed inline** — keep the refactor clean; flag bugs for a separate change.

## Output
The refactored code (tests green), plus a summary: the smells removed, the transformations applied, proof behaviour is unchanged (tests), and any bugs spotted (to handle separately). Hand to `/create-report`.
