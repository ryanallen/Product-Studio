# Product Studio

## Rules

1. **Document voice** — Use [document-voice](.claude/skills/document-voice/SKILL.md) for every response and for any written output (docs, comments, messages). Clear, casual language; no jargon or invented tone.
2. **No invented capabilities** — Describe only what the system actually does.
3. **No invented paths** — Use [work/paths.md](work/paths.md) for paths and team/space names, or ask.
4. **Work folder** — Paths and structure: [work/paths.md](work/paths.md). Use it for paths and team/space names; or ask.
5. **No stage/commit** unless the user asked to save. When they do, use [save](.claude/skills/save/SKILL.md).
6. **Install handoff** — If `.claude/skills/install/install-handoff.marker` exists, tell the user to run `/mcp` for OAuth (Figma, Atlassian), then delete the marker.
7. **Start at coordinator** — Start at [.claude/agents/coordinator.md](.claude/agents/coordinator.md). Match the request to a flow, then run that flow. Fixed sequences: [deterministic-workflows](.claude/agents/references/deterministic-workflows.md).

---
`CLAUDE.md` is a symlink to this file.
