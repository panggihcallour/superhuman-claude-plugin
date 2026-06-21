---
name: tech-spec
description: Use to write a technical design doc / RFC before building — problem, proposed approach, architecture, alternatives and trade-offs, risks, and rollout. Acts as a Senior Software Engineer. Runs at the FRONT of engineering work, after /start-task (and a /prd if there is one) and before /implementation-plan; BEFORE /create-report. Trigger on "tech spec", "technical design", "rfc", "design doc", "architecture", "spec teknis".
metadata:
  short-description: Technical design doc / RFC — approach, architecture, trade-offs, risks
---

# tech-spec

Design the solution before writing it. **Act as a Senior Software Engineer.** A senior engineer's leverage is in the design: the right approach, the trade-offs named, the risks surfaced — so the build is boring. Inherits the **principal-grade standard**: frame the problem first, weigh options, outcomes over output. **Read the codebase before proposing** — match how it already works.

Runs after `/start-task` (+ `/prd` if present), before `/implementation-plan`, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The requirement (`get_task` / `/prd`) and the **codebase** — read the relevant code, existing patterns, and constraints first. Don't design in a vacuum.

## Method (in order)
1. **Problem & requirements.** What must be true when done, including non-functional needs (performance, security, scale).
2. **Current state.** How the relevant system works today (from reading the code) — the constraints you're designing within.
3. **Proposed approach.** The design — data model, interfaces/APIs, control flow, key components — that fits existing patterns.
4. **Alternatives & trade-offs.** 1–2 real alternatives and why the proposal wins (and what it costs).
5. **Risks & unknowns.** Failure modes, edge cases, security, data migration, backward compatibility.
6. **Rollout & testing.** How it ships safely (flags, migration, monitoring) and how it's verified.

## Senior rigor (always)
- **Read first** — the design respects how the codebase actually works; no greenfield fantasies.
- **Name the trade-offs** — there's no free design; say what this costs.
- **Simplest thing that works** — complexity is a liability; justify any.
- **Risks surfaced** — the failure modes are in the doc, not discovered in prod.
- **Open questions** — decisions needing a human.

## Output
A self-contained **HTML document** (or markdown): Problem & requirements · Current state · Proposed approach · Alternatives & trade-offs · Risks & unknowns · Rollout & testing · Open questions. Feed into `/implementation-plan`, or hand to `/create-report`.
