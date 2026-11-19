# Superhuman Agent — Claude plugin

**Superhuman Agent** connects Claude to the **Superhuman Operations** MCP (tasks, projects,
workload, documents) and brings a roster of **senior specialist agents** to work those tasks —
all in one install. `start-task` reads a task, picks the right specialist, and runs the work.

> **Operational surface only.** This connects to the Operations MCP — tasks, projects, workload,
> documents. It exposes **no finance, sales, or people data / money**. You sign in with your own
> Ops account (OAuth) and get the tools your role has in the app; without signing in it
> returns nothing.

## The agents

| Agent | Persona | Specialises in | Status |
|---|---|---|---|
| **Product Agent** | Senior Product Manager | the what & why — problem framing, PRDs/specs, user stories & acceptance criteria, prioritisation, roadmap, success metrics, scope | **live** (7 skills) |
| **Design Agent** | Senior Principal UX Designer | how it works & feels — IA, sitemaps, flows, wireframes, visual design, design systems, prototyping, design QA | **live** (18 skills) |
| **Graphic Agent** | Senior Brand & Graphic Designer | brand & graphic — strategy, moodboard, logo, identity system, marketing assets, brand book, handoff, critique | **live** (8 skills) |
| **Dev Agent** | Senior Software Engineer | shipping code — implementation, review, refactors, tests, debugging | **live** (7 skills) |
| **Research Agent** | Senior UX & Market Researcher | evidence — user/market research, synthesis, usability, opportunity framing | **live** (7 skills) |

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

**Product Agent skills (live):**
- **Frame & discover** — `product-brief` · `pr-faq` · `product-discovery`
- **Define & plan** — `prd` · `prioritization` · `roadmap`
- **QA** — `product-critique`

**Dev Agent skills (live):**
- **Design & plan** — `tech-spec` · `implementation-plan`
- **Build** — `implement` · `test-plan`
- **Review & maintain** — `code-review` · `refactor` · `debug`

**Research Agent skills (live):**
- **Plan** — `research-plan` · `market-analysis`
- **Fieldwork** — `user-interview` · `survey` · `usability-eval`
- **Synthesise** — `synthesis` · `insights-report`

You need an active Ops account (founder, PM, designer or developer). No token: Claude asks you to sign in.

## Install

### A) Marketplace (recommended — no clone, no manual files)

In Claude (Desktop or Code):

```
/plugin marketplace add panggihcallour/superhuman-claude-plugin
/plugin install superhuman-agent@callour
```

Then restart Claude and sign in (below). Updates later: `/plugin marketplace update callour`.

### B) Local upload (Claude Desktop)

1. Download **[`superhuman-agent.zip`](./superhuman-agent.zip)** from this repo.
2. In Claude Desktop: **Directory → Plugins → Upload local plugin** → drop the zip → **Upload**.
3. Restart Claude and sign in (below).

## Sign in

The plugin connects to the Operations MCP with your own Ops account (OAuth), so there is no token
to copy or keep secret.

- **Claude Code:** run `/mcp`, pick `superhuman_operations` and choose **Authenticate**. The browser
  opens: sign in to Ops if asked, then **Allow**.
- **Claude Desktop:** the first time the connector is used, Claude opens the same sign-in. If it
  doesn't, open **Settings → Connectors**, find `superhuman_operations` and click **Connect**.

> **Upgrading from 0.11 or older?** Old `shmcp_` tokens no longer work. Update the plugin, and
> remove `SUPERHUMAN_MCP_TOKEN` from `~/.zshrc` (and `launchctl unsetenv SUPERHUMAN_MCP_TOKEN`).

## Use

- `/start-task` — paste a task link; it reads the task, moves it to in-progress, and kicks off, then either hands you the wheel or runs the full process.
- `/create-report` — when done, it reports the **process + outcome** (what it explored, the decisions, then the deliverable), posts it to the task under your name, then adds a progress update that tags the PM (after you approve).

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
- **MCP not connecting?** Sign in again (Claude Code: `/mcp` → `superhuman_operations` →
  Authenticate). MCP servers load at startup, so restart Claude after updating the plugin.
  Use an interactive chat.
