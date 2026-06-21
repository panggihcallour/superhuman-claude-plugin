---
name: competitive-audit
description: Use to research and tear down how competitors / reference products solve a problem — patterns, flows, strengths, weaknesses, and applicable takeaways — via web search. Acts as a Senior Principal UX Designer. Runs early, AFTER /start-task and usually BEFORE /explore-solutions, and BEFORE /create-report. Trigger on "competitive audit", "competitor analysis", "teardown", "riset kompetitor", "bandingin produk lain", "benchmark UX".
metadata:
  short-description: Web-research competitor / reference teardown with applicable takeaways
---

# competitive-audit

Tear down how other products solve the problem in the brief, and extract what we should borrow, avoid, and beat. **Act as a Senior Principal UX Designer** — judge patterns, don't just catalogue them.

Design WORK — runs **between `/start-task`** and **`/create-report`**, early in the process so its findings can feed `/explore-solutions`, `/information-architecture`, and `/wireframe`. Work in chat; nothing posts until the human approves.

## Inputs

- The active task's brief: `get_task` (+ `list_agent_queue` / `read_project_resource`) — the problem, users, and what "good" means.
- **`WebSearch`** is the research engine. Search for the named competitors if the brief lists them; otherwise search for the product category, the specific flow ("X onboarding flow", "X pricing page"), and best-in-class references. Use `WebFetch` to read a specific page in depth. (Do **not** pull from internal Dribbble/Behance — this skill is web-research-driven.)

## Method (in order)

1. **Scope.** Decide what you're comparing — the whole product, or one flow/surface from the brief. Pick 3–6 references: direct competitors + 1–2 best-in-class from outside the category.
2. **Research each** via web search: what they do, the actual flow/steps, the patterns and components they use, their copy/tone, and where they clearly invested vs cut corners. Cite the source URL for each claim.
3. **Judge, don't list.** For each reference note **what works** (and why) and **what fails** (and why) against *our* users and goals — not in the abstract.
4. **Find the patterns.** What's the convention everyone follows (break it only with reason)? Where's the divergence, and who's right? What's the table-stakes set users will expect?
5. **Extract takeaways.** Concrete: patterns to adopt, anti-patterns to avoid, and the gap/opportunity where we can beat them.

## Senior rigor (always)

- **Evidence:** every claim cites a source URL; flag where you're inferring vs confirming.
- **Relevance:** judge against *our* brief's users and success criteria, not generic "best practice".
- **Conventions vs differentiation:** name what to keep standard (don't make users relearn) and where it's worth being different.
- **Recency:** note when a reference may be outdated; UI changes fast.
- **Open questions:** what you couldn't verify and what the founder should weigh in on.

## Output

A self-contained **HTML document** (inline CSS, clean, grayscale): Objective · Reference set (with links) · Per-reference teardown (works / fails) · Pattern findings (conventions vs divergence) · Takeaways (adopt / avoid / opportunity) · Open questions. Show it in chat, iterate, then hand to `/create-report`.
