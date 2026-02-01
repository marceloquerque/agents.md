# AGENTS.md

> **Note:** Inspired by [@steipete's AGENTS.md](https://github.com/steipete/agent-rules), but this is my own heavily opinionated version. The original sparked the idea. Everything here reflects how *I* want agents to work. Optimized for autonomous agents, with accountability protocols. Fork it, remix it, make it yours.

Agent protocol rules for Codex/Claude/Cursor.

## What is AGENTS.md?

A single file that shapes how AI coding assistants behave in your workspace. Drop it in your repo root and agents (Claude, Cursor, Codex) automatically pick up the rules.

### What it does

- **Communication style** — Forces telegraph-style responses; no filler, minimal tokens. Agents greet you with one motivating line, then get to work.
- **Git safety** — Conservative by default. No destructive ops without explicit consent. Uses `gh` CLI for GitHub interactions. Conventional Commits enforced.
- **Guardrails** — Files stay under ~400 LOC. Deletes use `trash`. No enterprise over-engineering. Simplicity first.
- **Autonomy gate** — Agents don't ask "should I continue?" They keep going unless stuck on a truly blocking question. Opinionated defaults get documented, not debated.
- **Skills integration** — Agents check for available skills (React best practices, etc.) before creating plans. First-party knowledge over web searches.
- **Error philosophy** — Expected errors use result types. Unexpected errors fail loud. No silent fallbacks.
- **Critical thinking** — Fix root causes. Read more code when unsure. Call out conflicts instead of guessing.
- **User notes** — A living section at the bottom for persistent notes across sessions.

## Usage

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/robinebers/agents.md/main/AGENTS.md
```

To update it later, just ask to `Update the agents to the latest version` and it will fetch and merge into your local one.

Agents automatically read `AGENTS.md` from your workspace root.

Customize it—that's the point.
