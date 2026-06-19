---
name: post-comment
description: Use at the END of working a Superhuman Operations task in Claude Desktop to document the outcome onto the task. Summarizes THIS conversation into a decisions-first comment plus the final deliverable, posts it authored by the right agent, ticks the checklist, and moves the task to client_review. Handles a fresh deliverable or a revision. Always stops at a preview for you to approve ("rilis") before anything posts. Trigger when the user says "post comment", "post-kan", "rilis ke task", "dokumentasikan", or finishes work on a task.
---

# post-comment

Document the outcome of a work session onto a Superhuman task. The principle: **the comment is documentation of the OUTCOME, not a transcript.** Capture the decisions (which direction was chosen, what changed and why) plus the final file — not the back-and-forth.

Tools are from the Superhuman Operations MCP connector (Ops): `get_task`, `list_agent_queue`, `post_agent_artifact`, `prepare_agent_attachment_upload`, `finalize_agent_attachment`.

## Steps

1. **Identify the task.** Use the active `task_id` from this session (the one `/start-task` opened). If unknown, resolve it with `get_task` or ask.

2. **Revision?** If the task already has a prior artifact + reviewer feedback (a fresh `@<Agent>` mention), read `recent_comments` + `latest_artifacts` via `list_agent_queue` first, so the summary references what feedback you addressed. On a revision, mention `revision_requested_by` (the person who left the feedback), NOT the PM.

3. **Assemble the deliverable from this conversation:**
   - Text/research/doc → `post_agent_artifact` with `format: "html"` (self-contained doc, inline CSS, no external assets) or `"markdown"`.
   - Work done in Figma → `format: "figma"` + `figma_url`.
   - Image / binary files (logo concepts, PDFs) → `prepare_agent_attachment_upload` (per file) → PUT the bytes → `finalize_agent_attachment`. For an HTML doc WITH supporting images, attach the images first (`move_to_review: false`), then post the HTML.

4. **Write the completion comment.** FIRST PERSON ("I" / "aku"), 2-3 sentences, **decisions-first** (what was decided / changed and why), and `<mention>Name</mention>` the right person (assignee/PM on a fresh task, `revision_requested_by` on a revision). Never third-person self-reference ("the Design Agent did X" — say "I did X").

5. **Pick the agent slug** matching the work: `des` (design / art direction), `research`, `strategic`, `developer`, `graphic`. Default to the task's `assigned_agent`. Pass `runner: "claude"` and the `model` id for honest provenance.

6. **Preview, then stop.** Call `post_agent_artifact` (or `finalize_agent_attachment`) WITHOUT `confirm`. Show the user exactly what will happen: comment posted as <agent>, file attached, checklist ticked, status → `client_review`. STOP and ask: **rilis, revisi, atau batal?**

7. **On approval:**
   - "rilis" → call again with identical args + `confirm: true`.
   - "revisi [x]" → adjust the artifact/comment, preview again.
   - "batal" → do nothing; the task is untouched.

## Guardrails

- Never set `confirm: true` on your own — the human says "rilis" first.
- The comment documents the outcome; never paste the chat transcript.
- One artifact post at the END of the session, not progress comments along the way.
- `client_review` means "ready for the PM/founder to review", NOT "sent to the client" — the client-facing send stays a separate human step.
