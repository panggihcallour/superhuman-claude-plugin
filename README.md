# Design Agent — Claude plugin

A **Design Agent** plugin for [Callour Studio](https://callourstudio.com). It connects Claude to
the **Superhuman Operations** MCP (tasks, projects, workload, documents) and adds skills to run a
task and produce senior UX design deliverables — acting as a **Senior Principal UX Designer**.

It bundles the `superhuman_operations` MCP server (auto-registered on install) and a **19-skill,
end-to-end design process** you invoke as slash commands:

- **Start / document** — `start-task` (read a task, flip it to in-progress, frame the brief, kick off) · `post-comment` (summarise + post the deliverable back to the task)
- **Discover & define** — `competitive-audit` (web-research teardown) · `explore-solutions` (diverge into distinct directions + alternative flows)
- **Structure** — `information-architecture` · `sitemap`
- **Content** — `ux-writing`
- **Produce** — `wireframe` · `design-tokens` · `component-spec` · `visual-design` · `prototype` · `figma-build` (build it in Figma via the Figma MCP)
- **Document** — `design-spec` (convert a design into a `design.md` handoff)
- **QA gates** — `design-critique` · `wcag-check` · `edge-cases` · `figma-audit` · `design-parity`

Every design skill acts as a **Senior Principal UX Designer**.

> **Operational surface only.** This connects to the Operations MCP — tasks, projects, workload,
> documents. It exposes **no finance, sales, or people data / money** (the token is
> audience-scoped to Operations). The MCP endpoint requires a valid token; without one it
> returns nothing.

You need a **Superhuman MCP token** — ask the founder (minted at `/account/mcp`, founder-only).

## Install

### A) Marketplace (recommended — no clone, no manual files)

In Claude (Desktop or Code):

```
/plugin marketplace add panggihcallour/superhuman-claude-plugin
/plugin install design-agent@callour
```

Then set your token (below) and restart Claude. Updates later: `/plugin marketplace update callour`.

### B) Local upload (Claude Desktop)

1. Download **[`design-agent.zip`](./design-agent.zip)** from this repo.
2. In Claude Desktop: **Directory → Plugins → Upload local plugin** → drop the zip → **Upload**.
3. Set your token (below) and restart Claude.

## Set your token

The plugin authenticates with `Authorization: Bearer ${SUPERHUMAN_MCP_TOKEN}`, so that env var
must be visible to Claude. **Get the token from the founder first** (they mint it at `/account/mcp`).

**Claude Code (terminal).** Open your shell profile in a text editor:

```
open -e ~/.zshrc
```

TextEdit opens — add this line at the bottom (replace `shmcp_xxxx` with your token), then save (Cmd+S):

```
export SUPERHUMAN_MCP_TOKEN=shmcp_xxxx
```

Open a new terminal and run `claude` again.

**Claude Desktop (GUI app).** It doesn't read your shell profile, so set it for the login session
via Terminal, then restart Claude:

```
launchctl setenv SUPERHUMAN_MCP_TOKEN shmcp_xxxx
```

## Use

- `/design-agent:start-task` — paste a task link; Claude reads it, moves it to in-progress, and kicks off.
- `/design-agent:post-comment` — when done, it summarises the work and posts it to the task (after you approve).

Verify it's connected: paste a task link and ask Claude to `get_task <link>` — it should return
the task's title and status.

---

For the **Codex** version of this plugin, see
[superhuman-codex-plugin](https://github.com/panggihcallour/superhuman-codex-plugin).

## Notes & troubleshooting

- **No custom icon.** Claude's plugin manifest has no icon field, so the plugin uses Claude's
  default icon. Not changeable from the plugin side.
- **Display name "Design Agent"** shows in the `/plugin` picker on Claude v2.1.143+; older versions
  fall back to the id `design-agent`.
- **Updates are NOT automatic.** Run `/plugin marketplace update callour` to pull a new version.
- **Token on Claude Desktop:** a GUI app doesn't inherit your shell env — use
  `launchctl setenv SUPERHUMAN_MCP_TOKEN <token>` then restart Claude. From Claude Code (terminal),
  `export SUPERHUMAN_MCP_TOKEN=...` before launching works.
- **MCP not connecting?** Restart Claude after setting the token; MCP servers load at startup.
  Use an interactive chat.
