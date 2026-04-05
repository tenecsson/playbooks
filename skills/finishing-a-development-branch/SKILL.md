---
name: finishing-a-development-branch
description: Use when implementation is complete, tests are passing, and you need to choose merge, PR, keep, or discard workflow
---

Finish the branch only after fresh verification.

Workflow:
1. Run the full verification command now. If it fails, report the failure and stop.
2. Determine the base branch.
3. Present exactly this menu:

```text
Implementation complete. What would you like to do?

1. Merge back to <base-branch> locally
2. Push and create a Pull Request
3. Keep the branch as-is (I'll handle it later)
4. Discard this work

Which option?
```

Execution rules:
- Option 1: switch to the base branch, update it, merge, rerun verification on the merged result, delete the feature branch, remove the worktree.
- Option 2: push the branch, open the PR, report the PR location, keep branch and worktree unless the user asks to clean them up.
- Option 3: report the branch name and worktree path, keep both.
- Option 4: require the exact typed confirmation `discard` before deleting anything, then delete the branch and remove the worktree.

Never:
- offer completion options before verification
- delete work without explicit confirmation
- force-push unless the user explicitly requests it
