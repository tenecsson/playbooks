---
name: requesting-code-review
description: Use when a task, feature, or branch needs an explicit review pass before more implementation or before merge
---

Request focused review early enough to catch issues while they are cheap.

Use this after a major task, before merge, or when a fresh technical read would help.

Workflow:
1. Choose the diff range to review.
2. Launch the reviewer with `code-reviewer.md`.
3. Provide:
   - what was implemented
   - the plan or requirements
   - `BASE_SHA`
   - `HEAD_SHA`
   - a short description of the change
4. Act on the result:
   - fix Critical issues immediately
   - fix Important issues before proceeding
   - handle Minor issues deliberately
   - push back when the review is technically wrong

Do not skip review because the change feels simple.
