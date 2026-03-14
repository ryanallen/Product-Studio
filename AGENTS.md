# Product Studio

## Rules

1. **Verify task** — Before any Read, Write, Grep, or Shell: run `npm run checklist -- "<user request or summary>"`. The checklist step list is fixed by [scripts/checklist.ts](.claude/skills/verify-task/scripts/checklist.ts). After each skill you run, strikethrough it in the current task section and add a note. [verify-task](.claude/skills/verify-task/SKILL.md)
2. **Document voice** — Use [document-voice](.claude/skills/document-voice/SKILL.md) for every response and for any written output (docs, comments, messages). In the task checklist this is always Step 2; strikethrough when applied.
3. **No invented capabilities** — Describe only what the system actually does.
4. **No invented paths** — Use [work/paths.md](work/paths.md) for paths and team/space names, or ask.
5. **No stage/commit** unless the user asked to save. When they do, use [save](.claude/skills/save/SKILL.md).
6. **Install handoff** — If `.claude/skills/install/install-handoff.marker` exists, tell the user to run `/mcp` for OAuth (Figma, Atlassian), then delete the marker.

**Workflow.** Start at [.claude/agents/coordinator.md](.claude/agents/coordinator.md). Step 1 is verify task (checklist). Fixed sequences: [deterministic-workflows](.claude/agents/references/deterministic-workflows.md).

**Work folder.** Paths and structure: [work/paths.md](work/paths.md).

---
`CLAUDE.md` is a symlink to this file.
