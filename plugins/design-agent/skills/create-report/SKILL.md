---
name: create-report
description: Use at the END of working a Superhuman Operations task to create a report on it — not just the outcome, but the PROCESS: what was explored, the alternatives weighed, the decisions and why, then the final deliverable. Posts the report (authored by the right specialist) to the task, ticks the checklist, and moves it to client_review. Always previews for approval ("rilis") before posting. Trigger when the user says "create report", "buat report", "laporan", "selesaikan task", "akhiri task", "rilis ke task", "dokumentasikan", or finishes work on a task.
---

# create-report

Close a task by creating a **report** on it — the proper way to end work. A report is not just "here's the result": it documents the **process** — what was explored, the alternatives considered, what was tried and discarded, the decisions and their rationale — and then the deliverable. That's what makes the work auditable and the thinking reusable. It's a structured narrative, NOT a chat transcript.

This is the closer for every specialist (Design, Graphic, …). It runs at the END, after the work is done + approved in chat, and it's the ONLY thing written to Superhuman this session — everything before stayed in chat.

Tools (Superhuman Operations MCP): `get_task`, `list_agent_queue`, `post_agent_artifact`, `prepare_agent_attachment_upload`, `finalize_agent_attachment`.

## Steps

1. **Identify the task.** Use the active `task_id` from this session (the one `/start-task` opened). If unknown, resolve with `get_task` or ask.

2. **Revision?** If the task already has a prior artifact + reviewer feedback (a fresh `@<Agent>` mention), read `recent_comments` + `latest_artifacts` via `list_agent_queue` first. On a revision, the report leads with **how the feedback was addressed**, and you `<mention>` `revision_requested_by` (who left the feedback), NOT the PM.

3. **Write the report — process + outcome.** FIRST PERSON ("I" / "aku"), structured:
   - **Task** — the problem + brief, in a line or two.
   - **Process — what I explored.** The real journey: what was researched/explored, the alternatives or directions considered, what was tried and discarded. This is the part most write-ups skip — don't.
   - **Decisions & why.** The calls made and their rationale — tied to the brief, the user, and the trade-offs. Name what was deliberately NOT done.
   - **Deliverable.** The final output, clearly the result.
   - **Open questions / next steps.** What still needs a decision or a follow-up.
   Lead with the process + decisions; the deliverable is attached. Never third-person self-reference ("the Design Agent did X" → "I did X").

4. **Attach the deliverable:**
   - Text/doc → `post_agent_artifact` with `format: "html"` (self-contained, inline CSS, no external assets) or `"markdown"`.
   - Figma work → `format: "figma"` + `figma_url`.
   - Image/binary (logo concepts, PDFs) → `prepare_agent_attachment_upload` (per file) → PUT the bytes → `finalize_agent_attachment`. For an HTML doc WITH supporting images, attach images first (`move_to_review: false`), then post the HTML.

5. **Pick the agent slug** matching the work: `des` (design / art direction), `graphic`, `research`, `strategic`, `developer`. Default to the task's `assigned_agent`. Pass `runner: "claude"` + the `model` id for honest provenance.

6. **Preview, then stop.** Call `post_agent_artifact` (or `finalize_agent_attachment`) WITHOUT `confirm`. Show exactly what will happen: report posted as <agent>, file attached, checklist ticked, status → `client_review`. STOP and ask: **rilis, revisi, atau batal?**

7. **On approval:**
   - "rilis" → call again with identical args + `confirm: true`.
   - "revisi [x]" → adjust the report/artifact, preview again.
   - "batal" → do nothing; the task is untouched.

## Guardrails

- **Never set `confirm: true` on your own** — the human says "rilis" first.
- **Process, not just outcome** — a report that only shows the final file is incomplete; show the thinking (explored → weighed → decided).
- **Report, not transcript** — a structured narrative of the process, never the raw back-and-forth.
- **First person, as the specialist** — never refer to the agent in the third person.
- One report at the END of the session, not progress comments along the way.
- `client_review` means "ready for the PM/founder to review", NOT "sent to the client" — the client-facing send stays a separate human step.
