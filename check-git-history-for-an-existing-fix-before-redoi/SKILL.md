---
name: check-git-history-for-an-existing-fix-before-redoi
description: Before editing to fix a named failure, check `git log`/`git
metadata:
  source: learned by the auto-team, 2026-09-24
  verified: true
---
# Check git history for an existing fix before redoing it

Before editing to fix a named failure, check `git log`/`git blame`/`git diff --stat` to confirm the fix is not already committed, then verify with the exact acceptance command. If it is already fixed, report 'already done' with that command's raw output instead of writing a duplicate change.
