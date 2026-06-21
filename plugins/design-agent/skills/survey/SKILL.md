---
name: survey
description: Use to design a survey — clear unbiased questions, the right scales, sampling, and analysis plan — for attitudinal/quantitative measurement at scale. Acts as a Senior UX & Market Researcher. Runs as the quantitative fieldwork step, after /research-plan; BEFORE /create-report. Trigger on "survey", "questionnaire", "survey design", "nps", "rating scale", "kuesioner", "survei".
metadata:
  short-description: Survey design — unbiased questions, scales, sampling, analysis plan
---

# survey

Measure attitudes at scale without baking in the answer. **Act as a Senior UX & Market Researcher.** Surveys are attitudinal + quantitative — powerful for *how many / how much*, fragile to bad question design. The rigor is in unbiased wording, the right scale, and a sample you can trust. Inherits the **principal-grade standard**.

Runs after `/research-plan`, before `/create-report`. Work in chat; nothing posts until approved.

## Method (in order)
1. **Goal → measures.** What you must quantify (from `/research-plan`), and the specific metric each question yields.
2. **Write the questions.** Clear, single-barrelled, **non-leading**, neutral wording. One idea per question. Avoid jargon and assumptions.
3. **Choose scales deliberately.** Likert (agreement), rating, ranking, single/multi-select; consistent scale points; label them; include "N/A"/"don't know" where honest. Note when to use a validated instrument (e.g. SUS, NPS) vs a custom one — and their limits.
4. **Order & length.** Logical flow, sensitive questions late, demographics last; keep it short to protect completion.
5. **Sampling.** Who, how many (enough for the precision you need), how recruited, and the biases to watch (self-selection, non-response).
6. **Analysis plan.** How each question maps to a number + how you'll read it (don't over-claim significance on a small/biased sample).

## Senior rigor (always)
- **Unbiased wording** — no leading, loaded, or double-barrelled questions.
- **Scale fits the question** — and is labelled + consistent.
- **Sample you can trust** — size + recruiting match the claim you'll make.
- **Don't over-claim** — quantitative ≠ true if the sample/wording is flawed; state limits.
- **Open questions** — what the survey can't tell you (pair with qual).

## Output
A self-contained **HTML document**: Goal & measures · The questionnaire (questions + scales, ordered) · Sampling plan · Analysis plan + caveats · Open questions. Feed into `/synthesis`, or hand to `/create-report`.
