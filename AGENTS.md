# AGENTS

This repo is a compact library of reusable agent skills. Each skill is a small instruction module meant to change behavior, not pad context.

## Skills In This Repo

- `brainstorming`: turn an underdefined request into an approved design before implementation.
- `code-review`: perform or receive risk-based review without mandatory review rounds.
- `dispatching-parallel-agents`: split independent work across multiple agents without fragmenting tightly coupled problems.
- `implementation-quality`: choose proportionate tests and verification while rejecting brittle or tautological tests.
- `improve-coverage`: increase meaningful behavioral coverage without chasing the percentage.
- `planning-and-execution`: create durable plans when useful and execute approved plans without mandatory pauses.
- `systematic-debugging`: find root cause before proposing or applying fixes.
- `using-git-worktrees`: isolate work only when parallelism, experimentation, or risk justifies it.
- `writing-skills`: author or revise skills so they stay concise, discoverable, and behavior-changing.

## Skill Shape

Each skill lives at `skills/<name>/SKILL.md`.

Frontmatter supports only:
- `name`
- `description`

The description is a trigger sentence, not a summary. Start it with `Use when...`.

A good skill contains only:
- trigger conditions
- decision criteria and real invariants
- a workflow only when sequencing matters
- output contract
- minimal references

Sidecars are allowed, but only when loading them on demand is cheaper than keeping that material inline.

## House Style

Write for capable models. Be direct. Do not coach, flatter, or over-explain.

House rules:
- keep trigger conditions terse and easy to match
- assume capable models; do not restate generic engineering behavior
- prefer risk-based decision criteria over mandatory ceremony
- use hard rules only for safety, authorization, correctness invariants, or proven recurring failures
- include the terms a future model would search for: symptoms, triggers, tools, and error language
- preserve explicit user choices and do not infer worktrees, tests, reviews, commits, or pauses from ordinary implementation
- remove narrative history, duplicated reminders, and long examples
- keep always-loaded skills very short
- add sidecar prompts or references only when they save tokens in normal use

The style target is the same across the repo: concise instructions that materially change behavior without patronizing the model.

## How To Author A New Skill

Create a skill only for reusable, non-obvious judgment. Start from evidence such as observed sessions, repeated user corrections, a concrete failure, or a realistic high-risk scenario. Existing evidence is enough; do not require synthetic pressure runs for ordinary edits.

Write the smallest guidance that changes the bad decision. Validate structure after editing, and forward-test behavior only when uncertainty or risk justifies the added inference cost. Judge observable outcomes, not wording conformity.
