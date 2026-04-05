---
name: writing-plans
description: Use when a multi-step task needs an implementation plan before coding or before handing execution to another session or agent
---

Write plans that are short, executable, and verification-driven.

Do not use this when an approved plan already exists or when a tiny patch only needs an inline checklist.

Modes:
- Compact: 3-7 bullets for bounded work in the current session.
- Durable: save to `docs/plans/YYYY-MM-DD-<feature>.md` for larger work, reuse, or handoff.

Each task should be one meaningful checkpoint, roughly 10-30 minutes, and include:
- the goal
- exact files to create or modify
- key invariants or constraints
- verification commands
- sequencing or dependency notes when they matter

Rules:
- Prefer exact paths over vague areas.
- Prefer verification commands over narrative confidence.
- Include code only when it clarifies a tricky interface or algorithm.
- If design is still open, switch to `brainstorming` first.

After a durable plan, offer the execution path:
- implement here
- execute via a separate session or agent workflow
