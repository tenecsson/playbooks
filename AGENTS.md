# AGENTS

This repo is a compact library of reusable agent skills. Each skill is a small instruction module meant to change behavior, not pad context.

## Skills In This Repo

- `brainstorming`: turn an underdefined request into an approved design before implementation.
- `dispatching-parallel-agents`: split independent work across multiple agents without fragmenting tightly coupled problems.
- `executing-plans`: execute an approved plan in order, with verification checkpoints instead of re-planning.
- `finishing-a-development-branch`: decide whether to merge, open a PR, keep, or discard a branch after fresh verification.
- `receiving-code-review`: verify review feedback technically before applying it or pushing back.
- `requesting-code-review`: ask for focused review while changes are still cheap to fix.
- `subagent-driven-development`: execute an existing plan with fresh subagents per task and review gates between tasks.
- `systematic-debugging`: find root cause before proposing or applying fixes.
- `test-driven-development`: write the failing test first, then the smallest production change.
- `using-git-worktrees`: isolate feature work in a separate worktree before substantive changes.
- `using-playbooks`: load the minimum relevant skill set before exploring, planning, or coding.
- `verification-before-completion`: gather fresh evidence before claiming something is fixed or complete.
- `writing-plans`: produce short, executable, verification-driven plans.
- `writing-skills`: author or revise skills so they stay concise, discoverable, and behavior-changing.

## Skill Shape

Each skill lives at `skills/<name>/SKILL.md`.

Frontmatter supports only:
- `name`
- `description`

The description is a trigger sentence, not a summary. Start it with `Use when...`.

A good skill contains only:
- trigger conditions
- hard rules
- workflow
- output contract
- minimal references

Sidecars are allowed, but only when loading them on demand is cheaper than keeping that material inline.

## House Style

Write for capable models. Be direct. Do not coach, flatter, or over-explain.

House rules:
- keep trigger conditions terse and easy to match
- prefer hard rules over soft suggestions
- make workflows compact and executable
- include the terms a future model would search for: symptoms, triggers, tools, and error language
- remove narrative history, duplicated reminders, and long examples
- keep always-loaded skills very short
- add sidecar prompts or references only when they save tokens in normal use

The style target is the same across the repo: concise instructions that materially change behavior without patronizing the model.

## How To Author A New Skill

Treat skill authoring as TDD for instructions.

Authoring loop:
1. RED: run a pressure scenario without the skill and capture the failure or rationalization.
2. GREEN: write the smallest skill that blocks that failure.
3. VERIFY: rerun the scenario and confirm the skill changes behavior.
4. REFACTOR: tighten loopholes exposed by later failures.

Only create a skill when the pattern is reusable, non-obvious, and depends on judgment. Do not create skills for one-off fixes or project-local conventions.
