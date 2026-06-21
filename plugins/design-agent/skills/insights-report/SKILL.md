---
name: insights-report
description: Use to turn synthesised research into a decision-ready output — key insights, personas/JTBD, opportunities, and prioritised recommendations tied to the decision the research was meant to inform. Acts as a Senior UX & Market Researcher. Runs after /synthesis, near the END; BEFORE /create-report. Trigger on "insights report", "research report", "personas", "jobs to be done", "recommendations", "research findings", "laporan riset".
metadata:
  short-description: Decision-ready research output — insights, personas/JTBD, recommendations
---

# insights-report

Make the research change a decision. **Act as a Senior UX & Market Researcher.** A report that lists findings but doesn't drive action failed. The senior output is decision-ready: the few insights that matter, who the users are, the opportunities, and what to do — tied back to the question. Inherits the **principal-grade standard** — outcomes over outputs.

Runs after `/synthesis`, near the end, before `/create-report`. Work in chat; nothing posts until approved.

## Method (in order)
1. **Restate the decision.** The question the research was meant to inform — everything below serves it.
2. **Key insights.** The 3–5 insights that matter most (from `/synthesis`), each as a claim + evidence + confidence. Lead with these.
3. **Personas / JTBD (if relevant).** The user archetypes grounded in the data — real behaviours + jobs (*when [situation], they want to [motivation], so they can [outcome]*), not demographic clichés.
4. **Opportunities.** Where the insights point — unmet needs, pain points, openings — framed as opportunities, not features.
5. **Recommendations.** Prioritised, concrete next steps tied to each insight + the decision. What to do, what to stop, what to validate next.
6. **Limitations.** Sample, method, and confidence caveats — be honest about what this does and doesn't support.

## Senior rigor (always)
- **Decision-first** — the report answers the question; insights lead, raw data supports.
- **Grounded** — personas + opportunities trace to evidence, not invention.
- **Actionable** — recommendations are specific and prioritised, not "consider improving UX".
- **Honest about limits** — state confidence + caveats; don't oversell thin data.
- **Open questions** — what still needs research.

## Output
A self-contained **HTML document**: Decision · Key insights (claim · evidence · confidence) · Personas / JTBD · Opportunities · Prioritised recommendations · Limitations · Open questions. Hand to `/create-report`.
