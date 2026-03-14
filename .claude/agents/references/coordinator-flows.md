# Coordinator Flows

Fixed sequences. Each step is "run /command" or "delegate to agent". Coordinator Step 1 is verify task before picking a flow.

**Real commands:** `/checklist` = `npm run checklist -- "<request or summary>"`; `/clean` = `npm run clean` (empties `.tmp/`).

## Contents

Flows are listed alphabetically; Reference is last.

- [Analyst](#analyst)
- [Clean](#clean)
- [Clean up studio](#clean-up-studio)
- [Design / Figma](#design--figma)
- [Dev / TypeScript](#dev--typescript)
- [Discover](#discover)
- [Electron](#electron)
- [Electrobun](#electrobun)
- [Install](#install)
- [Learn](#learn)
- [Propose solutions](#propose-solutions)
- [Refine / document](#refine--document)
- [Research](#research)
- [Research Figma](#research-figma)
- [Save](#save)
- [Sync upstream](#sync-upstream)
- [Uninstall](#uninstall)
- [Update Figma token](#update-figma-token)
- [Update gitignore](#update-gitignore)
- [Reference](#reference)

---

## Analyst

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. analyst → analyst-diagnostics. Update checklist.

---

## Clean

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. Run `/clean` (or delegate cleaner → clean skill).

---

## Clean up studio

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. Ask user: clean everything or pick paths to verify.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
2. verifier → verify-docs then document-verification (report to `.tmp/verification-report.md`).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
3. Optionally cleaner → clean (delete `.tmp/` contents).

---

## Design / Figma

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. designer → designer-figma. Update checklist.

---

## Dev / TypeScript

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. developer → developer-typescript (and developer-check-types when the user wants type checking run). Developer may use developer-electrobun for Electrobun apps, developer-virtualization when it needs VM context (e.g. document flow). Update checklist after each skill.

---

## Discover

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. researcher → research.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
2. documenter → document.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
3. analyst → analyst-diagnostics.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
4. documenter → document (add problems).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
5. researcher → research (audit).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
6. documenter → document (current state).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
7. analyst → analyst-diagnostics (propose solutions).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
8. documenter → document (final pass).
Run [verify-task](.claude/skills/verify-task/SKILL.md).
9. documenter → document-ticket (comment on ticket).

---

## Electron

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. developer → developer-electron. Update checklist.

---

## Electrobun

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. developer → developer-electrobun. Update checklist.

---

## Install

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. installer → full install (config, choices, MCP, handoff, customizer if present).

---

## Learn

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. researcher → research.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
2. documenter → document (structure findings).

---

## Propose solutions

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. analyst → analyst-diagnostics.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
2. documenter → document (add problems to README).

---

## Refine / document

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. **When the user shared links or context that needs learning:** researcher → research (learn those links/context). Update checklist. Otherwise skip to step 2.
Run [verify-task](.claude/skills/verify-task/SKILL.md).
2. documenter → document. The documenter is the document subagent; it follows [document-agents](.claude/skills/document-agents/SKILL.md) for when to use which skills. It uses [document](.claude/skills/document/SKILL.md), [document-github](.claude/skills/document-github/SKILL.md) when the deliverable is a README, and [document-voice](.claude/skills/document-voice/SKILL.md). Update checklist after each skill. When doc work is done, documenter runs its end-of-job file review: research files in scope, add **Files in scope** to the checklist (name, location, content summary), review each file for needed updates, check off with notes.

---

## Research

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. researcher → research. Update checklist.

---

## Research Figma

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. researcher → research-figma. Update checklist.

---

## Save

1. verifier → verify-paths (compare work/paths.md Editable section Tree to disk; flag both directions).
2. If disk has paths not in tree: documenter → document-paths (add to tree only).
3. updater → save (stage and commit). No push.

---

## Sync upstream

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. updater → sync-upstream. Update checklist.

---

## Uninstall

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. uninstaller → uninstall. Update checklist.

---

## Update Figma token

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. updater → update-figma. Update checklist.

---

## Update gitignore

Run [verify-task](.claude/skills/verify-task/SKILL.md).
1. updater → update-gitignore (explain in plain language what's ignored, or update .gitignore / .git/info/exclude). Update checklist.

---

## Reference

[Coordinator](.claude/agents/coordinator.md) – Step 1 verify task (run `/checklist`), Step 2 match request to flow above, Step 3 execute that flow's steps in order.
