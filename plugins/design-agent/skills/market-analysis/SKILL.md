---
name: market-analysis
description: Use to analyse a market — sizing (TAM/SAM/SOM), trends, segments, competitors and positioning, and the opportunity — via web research. Acts as a Senior UX & Market Researcher. Runs early, after /start-task; BEFORE /create-report. Trigger on "market analysis", "market research", "market size", "tam sam som", "competitive landscape", "analisis pasar", "riset pasar".
metadata:
  short-description: Market analysis — sizing, trends, segments, competitors, opportunity
---

# market-analysis

Map the market the product plays in. **Act as a Senior UX & Market Researcher.** Distinct from a UX competitor teardown (`/competitive-audit`): this is the business landscape — size, trends, segments, where the opportunity is. Inherits the **principal-grade standard** — evidence over opinion, cite sources.

Runs early (after `/start-task`), before `/create-report`. Uses **`WebSearch`/`WebFetch`** for sourcing. Work in chat; nothing posts until approved.

## Method (in order)
1. **Scope the market.** Define the market/category precisely (whose problem, what alternatives count).
2. **Size it.** TAM / SAM / SOM with the assumptions + sources shown (top-down and/or bottom-up). Mark confidence — sizing is estimation, not fact.
3. **Trends & forces.** The shifts shaping the market (demand, tech, regulation, behaviour) and where it's heading.
4. **Segments.** The meaningful customer segments, their needs, and which are most attractive/under-served.
5. **Competitors & positioning.** Who's playing, how they position, where they cluster, and the **whitespace** to own.
6. **Opportunity.** The synthesised "so what" — where the defensible opportunity is, and the risks.

## Senior rigor (always)
- **Cite everything** — every number/claim has a source URL; flag inference vs fact.
- **Assumptions explicit** — sizing is a model; show the math + confidence, don't present a guess as truth.
- **Segment, don't generalise** — "the market" is several markets; name them.
- **Find the whitespace** — the output is an opportunity, not a data dump.
- **Open questions** — what you couldn't verify.

## Output
A self-contained **HTML document**: Market scope · Sizing (TAM/SAM/SOM + assumptions + sources) · Trends & forces · Segments · Competitors & positioning · Opportunity & risks · Open questions. Hand to `/create-report`.
