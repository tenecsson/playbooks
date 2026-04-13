---
name: brainstorming
description: Use when requirements, product choices, or technical approach are still underdefined and you need a design before implementation
---

Turn an open request into an approved design before coding.

Use this when:
- success criteria, constraints, or tradeoffs are still unclear
- the user wants help choosing architecture, behavior, or scope

Do not use this when:
- an approved design or implementation plan already exists
- the request is status, review, or verification only
- the patch is narrow and the desired behavior is already specified

Workflow:
1. Scan only the context needed to understand the problem.
2. Ask one clarifying question at a time. Prefer multiple choice when it genuinely helps.
3. If the design is open, present 2-3 approaches with tradeoffs and a recommendation. If it is bounded, present one recommended approach.
4. Describe the design at the right level: architecture, data flow, edge cases, and tests.
5. Get approval before implementation.
6. Write `docs/plans/YYYY-MM-DD-<topic>-design.md` only if the design needs durable reuse, review, or handoff.
7. If execution still needs a multi-step plan, switch to `writing-plans`. Otherwise implement directly.

Principles:
- Do not implement while material design questions remain open.
- Resolve real uncertainty, not imaginary uncertainty.
- Use the lightest process that closes the gap.
- Cut unneeded features early.
