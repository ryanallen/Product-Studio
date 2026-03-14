# Scripts dev review

| Script | Purpose |
|--------|---------|
| clean.mjs | Empties `.tmp/`. try/catch, exit(1) on error. |
| sync-codex-from-claude.mjs | Copies `.claude` → `.codex`. Requires `.claude`. |
| setup-figma-bridge.mjs | Packs figma-console-mcp, extracts bridge into skill scripts. |
| figma-desktop-bridge/code.js | Figma plugin runtime (sandbox). ES5; not Node. |
