# AGENTS.md

Start: say hi + 1 motivating line.
Work style: telegraph; noun-phrases ok; drop grammar; min tokens.

## Agent Protocol
- Contact: Robin Ebers (@robinebers, rob@robinebers.com).
- “Make a note” => edit AGENTS.md (Ignore `CLAUDE.md`, symlink for AGENTS.md).
- Editor: `cursor <path>`.
- New deps: quick health check (recent releases/commits, adoption).
- Style: telegraph. Drop filler/grammar. Min tokens.

## Guardrails
- Use `trash` for deletes.
- Bugs: add regression test when it fits.
- Keep files <~400 LOC; split/refactor as needed.
- Simplicity first: handle only important cases; no enterprise over-engineering.
- New functionality: small OR absolutely necessary.
- NEVER delete files or folders without explicit consent.
- MCPs: Use Exa to websearch early, and Ref to seek specific documention or web fetch.
- Quote exact errors; prefer 2024-2026 sources; fallback web server if unavailable

## Git
- Always use `gh` to communicate with GitHub.
- GitHub CLI for PRs/CI/releases. Given issue/PR URL (or `/pull/5`): use `gh`, not web search.
- Examples: `gh issue view <url> --comments -R owner/repo`, `gh pr view <url> --comments --files -R owner/repo`.
- Commits: Conventional Commits (`feat|fix|refactor|build|ci|chore|docs|style|perf|test`).
- CI: `gh run list/view` (rerun/fix til green).
- Safe by default: `git status/diff/log`. Push only when user asks.
- `git checkout` ok for PR review / explicit request.
- Branch changes require user consent.
- Destructive ops forbidden unless explicit (`reset --hard`, `clean`, `restore`, `rm`, …).
- No repo-wide S/R scripts; keep edits small/reviewable.
- Avoid manual `git stash`; if Git auto-stashes during pull/rebase, that’s fine (hint, not hard guardrail).
- If user types a command (“pull and push”), that’s consent for that command.
- Big review: `git --no-pager diff --color=never`.

## Language/Stack Notes
- Swift: use workspace helper/daemon; validate `swift build` + tests; keep concurrency attrs right.
- TypeScript: use repo PM; keep files small; follow existing patterns.
- Prefer TypeScript over Rust (team familiarity).

## Error Handling
- Expected issues: explicit result types (not throw/try/catch).
  - Exception: external systems (git, gh) → try/catch ok.
  - Exception: React Query mutations → throw ok.
- Unexpected issues: fail loud (throw/console.error + toast.error); NEVER add fallbacks.

## Backwards Compat
- Local/uncommitted: none needed; rewrite as if fresh.
- In main, unreleased: probably not; ask user.
- Released: probably needed.

## Critical Thinking
- Fix root cause (not band-aid).
- Unsure: read more code; if still stuck, ask w/ short options.
- Conflicts: stop. call out; pick safer path.
- Unrecognized changes: assume other agent; keep going; focus your changes. If it causes issues, stop + ask user.
- Leave breadcrumb notes in thread.

## User Notes
Use below list to store and recall user notes when asked to do so.

- (Replace this one when asked for first note)
