---
name: product-discovery
description: Use to de-risk a product idea before committing to build — surface the riskiest assumptions and validate the four product risks (value, usability, feasibility, business viability) with the cheapest tests. Acts as a Senior Product Manager. Runs after /product-brief (or /pr-faq) and before /prd; BEFORE /create-report. Trigger on "product discovery", "validate the idea", "assumptions", "de-risk", "discovery", "is this worth building".
metadata:
  short-description: De-risk via the four product risks (value/usability/feasibility/viability)
---

# product-discovery

Find out if it's worth building before you build it. **Act as a Senior Product Manager.** Per SVPG, discovery is separate from delivery: you validate the idea cheaply first. Inherits the **principal-grade standard** — evidence over opinion, outcomes over output, solve the problem (don't just ship the feature).

Runs after `/product-brief` / `/pr-faq`, before `/prd`, before `/create-report`. Work in chat; nothing posts until approved.

## Inputs
The brief + PR-FAQ. The riskier/bigger the bet, the more discovery it needs.

## Method (in order)
1. **List the assumptions.** Everything that must be true for this to work — write them down, don't assume them.
2. **Rank by risk.** Which assumption, if wrong, kills the idea? Sort by (impact × uncertainty). Tackle the riskiest first.
3. **Map to the four product risks:**
   - **Value** — will users want/need it? (the most common reason products fail)
   - **Usability** — can they figure out how to use it?
   - **Feasibility** — can we build it with what we have?
   - **Business viability** — does it work for the business (legal, sales, cost, brand)?
4. **Pick the cheapest test per risk.** The smallest experiment that could disprove the assumption (prototype test, fake door, interview, spike, data pull) — not a full build.
5. **Decide.** Go / pivot / kill, with the evidence — or what to validate next.

## Senior rigor (always)
- **Disprove, don't confirm** — design tests to kill the idea, not flatter it.
- **Cheapest test that settles it** — discovery is about learning fast, not building.
- **All four risks** — teams over-index on feasibility and skip value; don't.
- **Open questions** — what's still unvalidated, ranked.

## Output
A self-contained **HTML document**: Assumptions (ranked by risk) · Four-risks map · Test per risk · Recommendation (go/pivot/kill) + what to validate next. Feed into `/prd`, or hand to `/create-report`.
