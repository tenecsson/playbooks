---
name: dispatching-parallel-agents
description: Use when 2 or more tasks are independent enough to investigate or implement in parallel
---

Use one agent per independent problem domain. Keep related failures together.

Use this when:
- multiple failures have different root causes
- tasks touch different files or subsystems
- each task can be understood without the others

Do not use this when:
- failures may share a root cause
- the work is still exploratory and not yet partitioned
- agents would edit the same files or rely on shared state

Workflow:
1. Group work by root cause, owned files, or subsystem.
2. Split only the work that is truly independent.
3. Give each agent a narrow, self-contained brief: exact scope, relevant errors or context, constraints, and expected report.
4. Run them in parallel.
5. Review every result, check for overlap or conflicts, then run the combined verification.

Prompt rules:
- Focus on one file, subsystem, or failure cluster.
- Include the concrete symptoms and success condition.
- State what the agent must return.
- Never say "fix everything."
