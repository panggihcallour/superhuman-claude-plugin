# Superhuman Agent — Claude plugin

**Superhuman Agent** connects Claude to the **Superhuman Operations** MCP (tasks, projects,
workload, documents) and brings a roster of **senior specialist agents** to work those tasks —
all in one install. `start-task` reads a task, picks the right specialist, and runs the work.

> **Operational surface only.** This connects to the Operations MCP — tasks, projects, workload,
> documents. It exposes **no finance, sales, or people data / money** (the token is
> audience-scoped to Operations). The MCP endpoint requires a valid token; without one it
> returns nothing.

## The agents

| Agent | Persona | Specialises in | Status |
|---|---|---|---|
| **Product Agent** | Senior Product Manager | the what & why — problem framing, PRDs/specs, user stories & acceptance criteria, prioritisation, roadmap, success metrics, scope | coming |
| **Design Agent** | Senior Principal UX Designer | how it works & feels — IA, sitemaps, flows, wireframes, visual design, design systems, prototyping, design QA | **live** (18 skills) |
| **Graphic Agent** | Senior Brand & Graphic Designer | brand & graphic — strategy, moodboard, logo, identity system, marketing assets, brand book, handoff, critique | **live** (8 skills) |
| **Dev Agent** | Senior Software Engineer | shipping code — implementation, review, refactors, tests, debugging | coming |
| **Research Agent** | Senior UX & Market Researcher | evidence — user/market research, synthesis, usability, opportunity framing | coming |

Shared by every agent: **`start-task`** (the conductor — understand a task, then do it yourself or
run the full pipeline) and **`create-report`** (report the **process + outcome** back on the task — what was explored, the decisions, then the deliverable). Each agent
works at a senior, principal level in its craft.

**Design Agent skills (live):**
- **Strategy & discovery** — `design-strategy` · `competitive-audit` · `explore-solutions`
- **Structure** — `information-architecture` · `sitemap`
- **Content** — `ux-writing`
- **Produce** — `wireframe` · `design-tokens` · `component-spec` · `visual-design` · `prototype` · `figma-build`
- **Document** — `design-spec`
- **QA** — `design-critique` · `wcag-check` · `edge-cases` · `figma-audit` · `design-parity`

**Graphic Agent skills (live):**
- **Strategy & direction** — `brand-strategy` · `moodboard`
- **Identity** — `logo-design` · `brand-identity`
- **Application** — `marketing-assets`
- **Document & handoff** — `brand-guidelines` · `asset-handoff`
- **QA** — `graphic-critique`

You need a **Superhuman MCP token** — ask the founder (minted at `/account/mcp`, founder-only).

## Install

### A) Marketplace (recommended — no clone, no manual files)

In Claude (Desktop or Code):

```
/plugin marketplace add panggihcallour/superhuman-claude-plugin
/plugin install superhuman-agent@callour
```

Then set your token (below) and restart Claude. Updates later: `/plugin marketplace update callour`.

### B) Local upload (Claude Desktop)

1. Download **[`superhuman-agent.zip`](./superhuman-agent.zip)** from this repo.
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

- `/start-task` — paste a task link; it reads the task, moves it to in-progress, and kicks off, then either hands you the wheel or runs the full process.
- `/create-report` — when done, it reports the **process + outcome** (what it explored, the decisions, then the deliverable) and posts it to the task (after you approve).

Verify it's connected: paste a task link and ask Claude to `get_task <link>` — it should return
the task's title and status.

---

For the **Codex** version of this plugin, see
[superhuman-codex-plugin](https://github.com/panggihcallour/superhuman-codex-plugin).

## Notes & troubleshooting

- **No custom icon.** Claude's plugin manifest has no icon field, so the plugin uses Claude's
  default icon. Not changeable from the plugin side.
- **Display name "Superhuman Agent"** shows in the `/plugin` picker on Claude v2.1.143+; older
  versions fall back to the id `superhuman-agent`.
- **Updates are NOT automatic.** Run `/plugin marketplace update callour` to pull a new version.
- **Token on Claude Desktop:** a GUI app doesn't inherit your shell env — use
  `launchctl setenv SUPERHUMAN_MCP_TOKEN <token>` then restart Claude.
- **MCP not connecting?** Restart Claude after setting the token; MCP servers load at startup.
  Use an interactive chat.
