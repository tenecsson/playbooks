---
name: receiving-code-review
description: Use when receiving code review feedback and you must verify it technically before implementing or pushing back
---

Review feedback is input, not an order. Verify first.

Process:
1. Read the full feedback before reacting.
2. Restate the technical requirement in your own words, or ask for clarification.
3. Verify the claim against the codebase, tests, and surrounding constraints.
4. Decide whether the feedback is correct for this codebase.
5. Then act: implement, push back with evidence, or escalate to the user.

Rules:
- If any item is unclear, clarify all unclear items before implementing any of them.
- Do not use praise, thanks, apology, or performative agreement as a substitute for technical evaluation.
- For external reviewers, check for context gaps, backward-compatibility issues, and YAGNI before implementing.
- If a reviewer asks for a "proper" feature, verify that the feature is actually needed or used.
- If your pushback was wrong, correct it briefly and implement the fix.
- Implement one item at a time and test each change.

GitHub:
- Reply to inline review comments in the thread, not as a top-level PR comment.
