# Coordinator Flows

Fixed sequences. Each step is "run /command" or "delegate to agent". Coordinator Step 1 is verify task (run `/checklist`) before picking a flow.

**Verify task** — Run checklist first: `npm run checklist -- "<user request or summary>"`. Do not run Read, Write, Grep, or Shell until the checklist has been run. After each skill: strikethrough that step in the current task section and add a note. See verify-task SKILL and checklist script in `.claude/skills/verify-task/`.

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

Run verify task skill.
1. analyst → analyst-diagnostics. Update checklist.

---

## Clean

Run verify task skill.
1. Run `/clean` (or delegate cleaner → clean skill).

---

## Clean up studio

Run verify task skill.
1. Ask user: clean everything or pick paths to verify.
Run verify task skill.
2. verifier → verify-docs then document-verification (report to `.tmp/verification-report.md`).
Run verify task skill.
3. Optionally cleaner → clean (delete `.tmp/` contents).

---

## Design / Figma

Run verify task skill.
1. designer → designer-figma. Update checklist.

---

## Dev / TypeScript

Run verify task skill.
1. developer → developer-typescript (and developer-check-types when the user wants type checking run). Developer may use developer-electrobun for Electrobun apps, developer-virtualization when it needs VM context (e.g. document flow). Update checklist after each skill.

---

## Discover

Run verify task skill.
1. researcher → research.
Run verify task skill.
2. documenter → document.
Run verify task skill.
3. analyst → analyst-diagnostics.
Run verify task skill.
4. documenter → document (add problems).
Run verify task skill.
5. researcher → research (audit).
Run verify task skill.
6. documenter → document (current state).
Run verify task skill.
7. analyst → analyst-diagnostics (propose solutions).
Run verify task skill.
8. documenter → document (final pass).
Run verify task skill.
9. documenter → document-ticket (comment on ticket).

---

## Electron

Run verify task skill.
1. developer → developer-electron. Update checklist.

---

## Electrobun

Run verify task skill.
1. developer → developer-electrobun. Update checklist.

---

## Install

Run verify task skill.
1. installer → full install (config, choices, MCP, handoff, customizer if present).

---

## Learn

Run verify task skill.
1. researcher → research.
Run verify task skill.
2. documenter → document (structure findings).

---

## Propose solutions

Run verify task skill.
1. analyst → analyst-diagnostics.
Run verify task skill.
2. documenter → document (add problems to README).

---

## Refine / document

Run verify task skill.
1. **When the user shared links or context that needs learning:** researcher → research (learn those links/context). Update checklist. Otherwise skip to step 2.
Run verify task skill.
2. documenter → document. The documenter is the document subagent; it follows [document-agents](../../skills/document-agents/SKILL.md) for when to use which skills. It uses [document](../../skills/document/SKILL.md), [document-github](../../skills/document-github/SKILL.md) when the deliverable is a README, and [document-voice](../../skills/document-voice/SKILL.md). Update checklist after each skill. When doc work is done, documenter runs its end-of-job file review: research files in scope, add **Files in scope** to the checklist (name, location, content summary), review each file for needed updates, check off with notes.

---

## Research

Run verify task skill.
1. researcher → research. Update checklist.

---

## Research Figma

Run verify task skill.
1. researcher → research-figma. Update checklist.

---

## Save

Run verify task skill.
1. verifier → verify-paths (compare work/paths.md Editable section Tree to disk; flag both directions).
Run verify task skill.
2. If disk has paths not in tree: documenter → document-paths (add to tree only).
Run verify task skill.
3. updater → save (stage and commit). No push.

---

## Sync upstream

Run verify task skill.
1. updater → sync-upstream. Update checklist.

---

## Uninstall

Run verify task skill.
1. uninstaller → uninstall. Update checklist.

---

## Update Figma token

Run verify task skill.
1. updater → update-figma. Update checklist.

---

## Update gitignore

Run verify task skill.
1. updater → update-gitignore (explain in plain language what's ignored, or update .gitignore / .git/info/exclude). Update checklist.

---

## Reference

[Coordinator](../coordinator.md) – Step 1 verify task (run `/checklist`), Step 2 match request to flow above, Step 3 execute that flow's steps in order.
