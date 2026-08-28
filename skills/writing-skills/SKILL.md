---
name: writing-skills
description: Use when creating, editing, or validating a reusable skill and you need to keep it concise, discoverable, and behavior-changing
---

Write instructions only where they improve decisions beyond the model's normal capability.

Create a skill only when the pattern is reusable, non-obvious, and depends on judgment. Do not create skills for one-off fixes or project-local conventions.

Before editing, identify evidence that behavior needs guidance: observed sessions, repeated user corrections, a concrete failure, or a realistic high-risk scenario. Existing evidence is sufficient; do not manufacture a ritualized test run.

Authoring rules:
- Frontmatter supports only `name` and `description`.
- `description` must say when to use the skill, not summarize its workflow.
- Start descriptions with `Use when...`.
- Make triggers discriminating; broad descriptions create recurring load cost.
- Assume the model can plan, code, communicate, and use tools. Include only non-obvious decision criteria, real invariants, and useful stopping conditions.
- Prefer risk-based guidance over mandatory sequences, attempt counts, menus, checkpoints, or approvals.
- Preserve explicit user choices, including requests to skip tests, reviews, worktrees, delegation, or documentation.
- Keep skills short and self-contained unless an on-demand sidecar saves normal-load context.
- Put reusable prompts or heavy reference in sidecar files only when that saves tokens on normal loads.
- Remove narrative history, duplicated reminders, and long examples.
- Do not duplicate behavior already guaranteed by system or developer instructions.

Validate structure after each edit. Forward-test behavior only when uncertainty or risk justifies the extra inference; use realistic requests and judge the outcome, not whether generated wording matches a template.
