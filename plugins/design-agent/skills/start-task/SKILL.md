---
name: start-task
description: Use to begin working on a Superhuman Operations task inside Claude Desktop. Reads the task in full (brief, checklist, brand guidelines, prior artifacts), silently flips its status to in_progress (NO comment posted), then gives an active kickoff — a sharp design brief (problem, users, success criteria, scope, constraints), its understanding of the task, clarifying questions, and suggestions for the founder. Trigger when the user says "kerjain task X", "mulai task X", "start task ...", or points at a Superhuman task to work on.
---

# start-task

Begin working a Superhuman Operations task. The principle: **Claude Desktop is the workspace, Superhuman is documentation only.** During the work session NOTHING is written to the task except the silent status flip below. All drafting and revision stays in this chat. The task only gets a comment at the very end, via `/post-comment`.

This is also where the **design brief** is framed — understanding a task properly *means* sharpening it into a problem, users, success criteria, scope, and constraints before any design work starts.

Tools are from the Superhuman Operations MCP connector (Ops): `get_task`, `list_agent_queue`, `read_project_resource`, `request_clarification`, `update_task`.

## Steps

1. **Identify the task.** From the user's request, resolve the task by title / short_code / id (+ project name if given). If it's ambiguous, look it up with `get_task` (title + project_name) or list a few candidates and ask which one. Hold onto the `task_id` for the rest of the session.

2. **Understand it deeply — read, don't skim.** Call `get_task` for the full body, checklist, tags, dates, effort. For real context (brand guidelines, prior artifacts, reviewer feedback, the brief the task references), call `list_agent_queue` and `read_project_resource(task_id, ref)`. You cannot frame a brief or advise well on a task you only skimmed.

3. **Flip status to in_progress, silently.** Call `update_task(task_id, status: "in_progress")` — NOT `claim_task` (it posts a kickoff comment, which breaks the documentation-only rule). `update_task` previews first; show it, get the OK, then call again with `confirm: true`.

4. **Deliver an active kickoff with a sharp brief — this is the point of the skill, not a dry recap.** In chat, give the founder:
   - **The brief** — frame the work before reacting to it:
     - **Problem** — what we're really solving, in one line.
     - **Users & jobs-to-be-done** — who it's for and what they're trying to get done.
     - **Success criteria** — how we'll know the design worked.
     - **Scope** — what's in, and what's explicitly out.
     - **Constraints** — brand, technical, deadline, dependencies.
     - **Assumptions** — what you're taking as given. Where the brief is silent, state your assumption rather than leaving a blank.
   - **Understanding** — the deliverable + checklist in your own words. Show you actually get it.
   - **Clarifications** — the open questions / decisions you need before or during the work. Ask the founder directly in chat (a conversation, NOT the `request_clarification` tool): ambiguous scope, a missing preference, a fork in approach.
   - **Masukan** — your take: a suggested approach, risks you see, an idea the brief missed, what you'd prioritise. Be opinionated. You are a collaborator, not a stenographer.

5. **Escalate to the PM only if truly blocked.** If a question can ONLY be answered by the PM / author / client (not the founder in chat) AND it blocks starting, use `request_clarification` (preview → confirm) to post it to the task, then wait. Otherwise keep clarifying in chat.

6. **Proceed.** Work in chat, folding in the founder's answers and the brief above. The brief is the contract every later step (IA, wireframe, visual design, …) is measured against. Nothing posts to Superhuman until `/post-comment`.

## Guardrails

- Never post a comment during the work session. The only Superhuman write here is the `in_progress` status flip (or a `request_clarification` if the brief is too thin).
- Never set `confirm: true` on your own — always preview, show the human, wait for approval.
- Remember the active `task_id` so `/post-comment` knows which task to document.
