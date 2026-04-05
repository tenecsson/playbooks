---
name: executing-plans
description: Use when you have an approved written implementation plan to execute, especially when work should happen in verified checkpoints
---

Execute the approved plan. Do not re-plan unless the plan has a real gap.

Workflow:
1. Read the plan once and review it critically. Raise actual blockers or contradictions before starting.
2. Set up tracking for the plan tasks.
3. Execute the smallest useful checkpoint, usually 1-3 tasks or one natural batch.
4. Run the verification named in the plan for each checkpoint.
5. Report what changed and the verification evidence.
6. After each checkpoint report, stop and wait for feedback unless the user explicitly asked for uninterrupted execution.
7. Repeat until the plan is complete.
8. Then use `finishing-a-development-branch`.

Stop and ask when:
- an instruction is unclear
- a dependency is missing
- verification keeps failing
- the plan is incomplete enough that execution would become guesswork

Rules:
- Follow the plan as written once it is approved.
- Use `using-git-worktrees` before starting isolated feature work.
- Do not start feature work on `main` or `master` without explicit consent.
