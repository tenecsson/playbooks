---
name: using-git-worktrees
description: Use when the user requests a worktree or parallel, experimental, or high-risk work needs isolation from the current checkout
---

Use a worktree only when isolation has concrete value. Do not create one merely because a task is a feature or follows a plan. Honor an explicit request to work in the current checkout.

Before creating one:
- inspect repository instructions and current worktree/branch state
- ensure concurrent agents will not edit the same files or depend on unshared state
- preserve existing user changes

Location order:
1. repo instructions that name a worktree location
2. existing `.worktrees/` in the repo root
3. existing `worktrees/` in the repo root
4. otherwise ask only if the location materially matters; default to `.worktrees/`

Rules:
- If using a repo-local worktree directory, verify it is ignored by git. If it is not ignored, fix that before creating the worktree.
- Create a dedicated branch unless the user requested a different safe arrangement.
- Run the repo's normal bootstrap or dependency install in the new worktree.
- Run a proportionate baseline check. If it fails, distinguish a pre-existing failure from one that blocks the requested work and report it.

Report the branch and path. Do not merge, remove, or delete the worktree without authorization from the task or the user.
