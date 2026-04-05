---
name: subagent-driven-development
description: Use when executing an existing implementation plan in the current session and the tasks are independent enough for fresh subagent execution
---

Use fresh subagents per task, with review gates after every task. Only use this when delegation is available and allowed.

Workflow:
1. Read the plan once. Extract every task, its context, and dependencies. Track them.
2. For each task:
   - dispatch a fresh implementer with the full task text and scene-setting context
   - answer questions before implementation continues
   - require tests, verification, self-review, a stable diff boundary for review, and a concrete report
   - run spec review
   - if spec review fails, send fixes back to the same implementer and re-review
   - only after spec passes, run code-quality review
   - if code-quality review fails, send fixes back to the same implementer and re-review
   - mark the task complete only after both reviews pass
3. After the last task, run one final whole-change review.
4. Then use `finishing-a-development-branch`.

Rules:
- Use `using-git-worktrees` before starting.
- Do not make implementers read the plan file; give them the task text directly.
- Do not run multiple implementers in parallel in the same workspace.
- Do not skip re-review loops.
- Spec review must pass before code-quality review starts.
- Before code-quality review, make sure `BASE_SHA` and `HEAD_SHA` are well-defined, usually by committing the task work.
- Use `test-driven-development` inside implementation tasks.

Sidecars:
- `implementer-prompt.md`
- `spec-reviewer-prompt.md`
- `code-quality-reviewer-prompt.md`
