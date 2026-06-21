---
name: implementation-plan
description: Use to break approved engineering work into a sequenced plan — steps/PRs, order, milestones, what to verify at each, and risks — before writing code. Acts as a Senior Software Engineer. Runs after /tech-spec and before /implement; BEFORE /create-report. Trigger on "implementation plan", "break this down", "plan the work", "sequencing", "rencana implementasi".
metadata:
  short-description: Sequenced build plan — steps/PRs, order, milestones, verification
---

# implementation-plan

Turn a design into a safe sequence of small steps. **Act as a Senior Software Engineer.** Big-bang changes are how things break; a senior engineer ships in reviewable, verifiable increments. Inherits the **principal-grade standard** — outcomes over output, explicit trade-offs.

Runs after `/tech-spec`, before `/implement`, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The tech spec (`/tech-spec`) or the agreed approach + the codebase. If there's no design, write the spec first.

## Method (in order)
1. **Slice into steps.** Decompose into the smallest independently-shippable, independently-reviewable units (PR-sized). Each step leaves the system working.
2. **Sequence.** Order by dependency + risk — de-risk the unknowns early; keep each step green.
3. **Per step:** what changes, what it depends on, how it's verified (tests/manual), and the rollback if it goes wrong.
4. **Milestones.** Group steps into meaningful checkpoints (e.g. "behind a flag", "migration done", "GA").
5. **Risks & coordination.** Migrations, feature flags, data backfills, anyone else's work it touches.

## Senior rigor (always)
- **Small + shippable** — each step is reviewable on its own and keeps main green.
- **Risk-first ordering** — validate the scary parts early, not last.
- **Verifiable** — every step says how you'll know it works.
- **Reversible** — flags/rollback for anything risky.
- **Open questions** — sequencing decisions needing a call.

## Output
A self-contained **HTML document** (or markdown): the ordered steps (each: change · depends-on · verify · rollback), milestones, and risks/coordination. Feed into `/implement`, or hand to `/create-report`.
