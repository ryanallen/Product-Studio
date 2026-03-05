---
name: document-verification
description: Track all files the verifier processed, compare to README and paths.md structure, and save a report to .tmp/ for user verification.
---

# Document Verification

1. **Input.** Receive from verifier: the list of all files that were checked and any issues found (heading hierarchy, nav, emojis).
2. **Compare to repo structure.** Read `README.md` (Repo Structure section) and `work/paths.md` if it exists. Compare the set of files processed to the structure described there: list any files in the report that are not mentioned in README/paths, and any paths in README/paths that were not processed.
3. **Write report.** Create `.tmp/` if it does not exist. Write a single report file (e.g. `.tmp/verification-report.md`) containing:
   - Date/time of run
   - Full list of files processed (system and projects)
   - Comparison to README and paths.md (matches, extra files, missing paths)
   - Per-file issues: heading hierarchy, nav, emoji
4. **Do not commit.** The report lives in `.tmp/` which is gitignored. User can verify the run and then use **cleaner** [clean](../clean/SKILL.md) to delete `.tmp/` contents if desired.
