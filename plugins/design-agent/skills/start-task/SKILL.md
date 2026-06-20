---
name: start-task
description: The daily entry point for working a Superhuman Operations task. Reads the task via the Operations MCP, understands it deeply, frames the design brief (problem/users/success/scope/constraints), silently flips it to in_progress, and gives an active kickoff — then FORKS: either you do it yourself (cherry-pick skills), or it conducts the whole design process end-to-end (strategy → solutions → structure → production → QA → post-comment) with gate checkpoints and parallel sub-agents. Trigger when the user says "kerjain task X", "mulai task X", "start task ...", "kerjain full", "jalanin pipeline desain", or points at a Superhuman task / task link.
---

# start-task

The single entry point for working a Superhuman Operations task. **Understand it first, then choose the depth:** stop after the kickoff and work it yourself, or hand the baton to the conductor and let it run the whole design process.

**Principle: Claude is the workspace, Superhuman is documentation only.** The ONLY Superhuman write during the session is the silent `in_progress` flip below. All drafting and revision stays in chat; the task gets a comment only at the very end, via `/post-comment`.

Tools: the **Superhuman Operations MCP** (`get_task`, `list_agent_queue`, `read_project_resource`, `request_clarification`, `update_task`, …) to read + move the task; the **Agent tool** to fan out parallel sub-agents (Claude Code); the design **skills** as phase playbooks.

> **Environment note.** The conductor's parallel phases need a sub-agent / fan-out capability (the **Agent tool**, native to Claude Code). Without it (e.g. Claude Desktop chat), run every phase **sequentially** in the conversation — it still works, just not parallelised.

## Part 1 — Understand & kick off (always)

1. **Identify the task.** Resolve it by title / short_code / id / shared URL (+ project name if given). If ambiguous, look it up with `get_task` or list candidates and ask. Hold the `task_id` for the whole session.
2. **Understand it deeply — read, don't skim.** `get_task` for the full body, checklist, tags, dates, effort. For real context (brand guidelines, prior artifacts, reviewer feedback, the referenced brief), `list_agent_queue` and `read_project_resource(task_id, ref)`.
3. **Flip status to in_progress, silently.** `update_task(task_id, status: "in_progress")` — NOT `claim_task` (it posts a comment, breaking the documentation-only rule). `update_task` previews first; show it, get the OK, then call again with `confirm: true`.
4. **Active kickoff with a sharp brief** — the point of Part 1, not a dry recap:
   - **The brief** — **Problem** (one line) · **Users & jobs-to-be-done** · **Success criteria** · **Scope** (in vs out) · **Constraints** (brand/tech/deadline/deps) · **Assumptions** (state them where the brief is silent).
   - **Understanding** — the deliverable + checklist in your own words.
   - **Clarifications** — open questions you need answered (ask the founder in chat — NOT `request_clarification`).
   - **Masukan** — your opinionated take: approach, risks, an idea the brief missed, what to prioritise.

## Part 2 — 🔱 Fork: drive yourself, or let me conduct

After the kickoff, offer the choice:
- **"kerjakan sendiri" / "aku sendiri aja" / stop** → done. The human cherry-picks individual skills (`/wireframe`, `/visual-design`, …) as they wish. This is the lightweight mode.
- **"lanjut" / "gas" / "kerjain full"** → propose a phase plan and run the pipeline in Part 3.

## Part 3 — The conductor (only if they chose to continue)

**Propose a phase plan first.** Not every task needs every skill — a logo/brand task ≠ a web-app feature ≠ a mid-project "Phase 4". Pick the ordered subset this task actually needs, say what you're **skipping and why**, and get approval before running anything.

Then run the approved phases, in order (Part 1 already did **A**):

- **A · Understand & frame** — done in Part 1.
- **B · Strategy & divergence** — `/design-strategy` (initiative-level only) → `/competitive-audit` → `/explore-solutions`. 🔒 **Gate:** pick a direction.
- **C · Structure** — `/information-architecture` + `/sitemap` (independent → parallel sub-agents) + `/ux-writing` if copy-heavy. 🔒 **Gate.**
- **D · Produce** — `/wireframe` → `/visual-design` → `/prototype` and/or `/figma-build`; add `/design-tokens` + `/component-spec` if a system is needed. Sequential — the designer steers each. 🔒 **Gate per major artifact.**
- **E · QA gates** — `/design-critique` + `/wcag-check` + `/edge-cases` (+ `/figma-audit` / `/design-parity` if Figma/a build exists). Independent → parallel sub-agents, then synthesise. 🔒 **Gate.**
- **F · Document & post** — `/design-spec` if a handoff is needed → `/post-comment` (preview → "rilis").

**How to run each phase:**
- **Interactive / judgment phases** (strategy, solutions, produce): run the skill **in this conversation** so the designer sees the reasoning and can steer.
- **Independent / parallel phases** (IA + sitemap; the QA gates): fan out **sub-agents** with the Agent tool — give each the one skill's instructions **plus** the brief/task context (don't assume it inherited the skills), collect deliverables, synthesise, then gate.

**Checkpoints — gates, not every phase.** Stop at the 🔒 gates (≈4–6 stops). At each: show what was produced, state what's next, wait for "lanjut" / edits. If the designer says run looser ("jangan berhenti tiap fase", "gas sampai QA"), collapse the gates. **Never** run unattended through a write to Superhuman.

## Guardrails

- **Documentation-only until the end:** the only Superhuman write is the silent `in_progress` flip (or a `request_clarification` if the brief is too thin).
- **Never set `confirm: true` on your own** — preview → show the human → wait.
- **Pick phases, don't force the whole suite** — match the task type; name what you skip and why.
- **Sub-agents get explicit instructions** — pass the phase's skill content + the brief; never assume a sub-agent inherited the skills.
- **Escalate to the PM only if truly blocked** — `request_clarification` (preview → confirm) for a question only the PM/author/client can answer that blocks starting; otherwise keep clarifying in chat.
- Remember the active `task_id` so `/post-comment` documents the right task.
