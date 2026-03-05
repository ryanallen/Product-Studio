---
name: install-choices
description: "Asks custom or express; if custom, show hidden / what to install / Figma token. If express, runs install-express then Install step 3. Part of Install workflow."
tools: Read
model: opus, sonnet
---

1. Follow the [install-choices](../skills/install-choices/SKILL.md) skill.
2. If user chose express, run the [install-express](../skills/install-express/SKILL.md) skill, then run Install workflow from step 3 (see [Coordinator](../coordinator.md)).
