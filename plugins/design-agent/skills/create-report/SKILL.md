---
name: create-report
description: Use at the END of working a Superhuman Operations task to create a report on it — not just the outcome, but the PROCESS: what was explored, the alternatives weighed, the decisions and why, then the final deliverable. Posts the report to the task as the person working it, then an Add progress update that tags the PM and moves the task to client_review. Always previews for approval ("rilis") before posting. Trigger when the user says "create report", "buat report", "laporan", "selesaikan task", "akhiri task", "rilis ke task", "dokumentasikan", or finishes work on a task.
---

# create-report

Close a task by creating a **report** on it — the proper way to end work. A report is not just "here's the result": it documents the **process** — what was explored, the alternatives considered, what was tried and discarded, the decisions and their rationale — and then the deliverable. That's what makes the work auditable and the thinking reusable. It's a structured narrative, NOT a chat transcript.

This is the closer for every specialist (Design, Graphic, …). It runs at the END, after the work is done + approved in chat, and it's the ONLY thing written to Superhuman this session — everything before stayed in chat. Everything posts as the person using the connector (their name on the comment), the same as typing it in the app.

Tools (Superhuman Operations MCP): `get_task`, `read_task_attachment`, `add_task_comment`, `add_progress`.

## Steps

1. **Identify the task.** Use the active `task_id` from this session (the one `/start-task` opened). If unknown, resolve with `get_task` or ask.

2. **Revision?** If `get_task`'s `recent_comments` hold reviewer feedback on an earlier deliverable, read it (and any feedback file in `files` via `read_task_attachment`) first. On a revision, the report leads with **how the feedback was addressed**, and you `<mention>` the person who left the feedback.

3. **Write the report — process + outcome.** FIRST PERSON ("I" / "aku"), structured:
   - **Task** — the problem + brief, in a line or two.
   - **Process — what I explored.** The real journey: what was researched/explored, the alternatives or directions considered, what was tried and discarded. This is the part most write-ups skip — don't.
   - **Decisions & why.** The calls made and their rationale — tied to the brief, the user, and the trade-offs. Name what was deliberately NOT done.
   - **Deliverable.** The final output, clearly the result.
   - **Open questions / next steps.** What still needs a decision or a follow-up.
   Lead with the process + decisions; the deliverable is linked. Write it as markdown (headings, **bold**, lists, links): it becomes rich text. Never third-person self-reference ("the Design Agent did X" → "I did X").

4. **Link the deliverable.** The connector doesn't upload files. Put the work where the team reads it and link it: Figma for design work, Google Drive / Docs for documents, PDFs and image sets. If the user wants a file on the task itself, they attach it in the app's task panel.

5. **Preview both posts, then stop.** Call WITHOUT `confirm`:
   - `add_task_comment(task_id, body)` with the report (markdown).
   - `add_progress(task_id, items)` with the deliverable as `done` items (each with its `link`) and any `in_progress` / `note` items. It greets + tags the project's PM and moves the task to `client_review`. If checklist items are still open the task stays where it is: say so, and the user ticks them in the app first.
   Show exactly what will happen: report comment, progress update to <PM>, status → `client_review`. STOP and ask: **rilis, revisi, atau batal?**

6. **On approval:**
   - "rilis" → call both again with identical args + `confirm: true`, the comment first.
   - "revisi [x]" → adjust the report, preview again.
   - "batal" → do nothing; the task is untouched.

## Guardrails

- **Never set `confirm: true` on your own** — the human says "rilis" first.
- **Process, not just outcome** — a report that only shows the final file is incomplete; show the thinking (explored → weighed → decided).
- **Report, not transcript** — a structured narrative of the process, never the raw back-and-forth.
- **First person** — it posts under the user's own name; never refer to an agent in the third person.
- One report at the END of the session, not progress comments along the way.
- `client_review` means "ready for the PM/founder to review", NOT "sent to the client" — the client-facing send stays a separate human step.
