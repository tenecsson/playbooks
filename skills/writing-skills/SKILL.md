---
name: writing-skills
description: Use when creating, editing, or validating a reusable skill and you need to keep it concise, discoverable, and behavior-changing
---

Treat skill authoring as TDD for instructions.

Create a skill only when the pattern is reusable, non-obvious, and depends on judgment. Do not create skills for one-off fixes or project-local conventions.

Authoring loop:
1. RED: run a pressure scenario without the skill and capture the failure or rationalization.
2. GREEN: write the smallest skill that blocks that failure.
3. VERIFY: rerun the scenario and confirm the skill changes behavior.
4. REFACTOR: tighten loopholes exposed by later failures.

Authoring rules:
- Frontmatter supports only `name` and `description`.
- `description` must say when to use the skill, not summarize its workflow.
- Start descriptions with `Use when...`.
- Use the keywords a future model would search for: symptoms, triggers, tools, and error language.
- For discipline-enforcing skills, test with 3+ combined pressures, capture rationalizations verbatim, and turn repeated excuses into explicit red flags or counter-rules.
- Keep always-loaded skills very short; keep most others short unless they truly need sidecars.
- Match the house style of `playbooks`: terse trigger conditions, hard rules, compact workflow, and sidecars only when they save tokens.
- Put reusable prompts or heavy reference in sidecar files only when that saves tokens on normal loads.
- Remove narrative history, duplicated reminders, and long examples.

A good skill contains only:
- trigger conditions
- hard rules
- workflow
- output contract
- minimal references
