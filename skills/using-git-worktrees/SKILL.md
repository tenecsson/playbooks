---
name: using-git-worktrees
description: Use when feature work needs an isolated workspace or before executing an implementation plan on a non-base branch
---

Create an isolated worktree before substantive feature work.

Directory selection order:
1. repo instructions that name a worktree location
2. existing `.worktrees/` in the repo root
3. existing `worktrees/` in the repo root
4. otherwise make `.worktrees/` in the repo root

Rules:
- If using a repo-local worktree directory, verify it is ignored by git. If it is not ignored, fix that before creating the worktree.
- Create a new branch with the worktree; do not work directly on `main` or `master` without explicit consent.
- Run the repo's normal bootstrap or dependency install in the new worktree.
- Verify the new worktree starts from a clean, passing baseline before making changes.
- If baseline verification fails, stop and ask before making changes.

Minimum sequence:
1. determine the location
2. create the worktree and branch
3. bootstrap the repo
4. run baseline verification
5. report the branch and path
