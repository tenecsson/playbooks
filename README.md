# Playbooks

`playbooks` is a distilled version of [obra/superpowers](https://github.com/obra/superpowers) for an era where models don't need to be patronized.

The goal is simple: keep the parts that actually change model behavior, and strip the rest.

What stays:
- reusable skill names and trigger conditions
- decision criteria and real invariants that improve outcomes
- compact workflows only where ordering matters
- sidecar files only when on-demand loading is cheaper

What goes:
- long persuasion
- narrative rationale
- repeated reminders
- bulky examples that waste prompt budget
- mandatory tests, reviews, worktrees, checkpoints, or approvals without a concrete need

Repo shape:
- `skills/<name>/SKILL.md`: the skill itself
- optional sidecars next to a skill when they save tokens
- `AGENTS.md`: how to use these skills and how to write new ones in the house style

The reduction is in instructions, not in the user-facing substance those instructions should produce.

Licensed under MIT. See `LICENSE`.
