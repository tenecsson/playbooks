---
name: systematic-debugging
description: Use when any bug, failing test, build break, or unexpected behavior needs root-cause analysis before fixes
---

Do not propose fixes before you understand the cause.

Process:
1. Evidence
   - read the actual error
   - reproduce the issue
   - inspect recent changes
   - if the system has multiple layers, instrument component boundaries so you can see where data, config, or state stops matching expectations
   - trace bad values backward to their source
2. Pattern
   - find a working example or reference
   - compare working and broken behavior line by line
   - list the real differences and dependencies
3. Hypothesis
   - state one concrete hypothesis
   - run the smallest experiment that can confirm or reject it
   - if it fails, discard it and form a new one; do not stack fixes
4. Fix
   - create a failing reproduction test or script
   - fix the root cause, one change at a time
   - for flaky async/tests, replace arbitrary sleeps with waits on the actual condition unless timing itself is what you are testing
   - after invalid-data or invalid-state bugs, add validation at each layer the bad data crosses so the bug is harder to reintroduce
   - rerun verification

Rules:
- No fixes without root-cause investigation first.
- No bundled "while I'm here" changes.
- If three fix attempts have failed, stop and question the architecture with the user before trying a fourth.
- If investigation shows the issue is external, timing-dependent, or environmental, document the evidence and add appropriate handling or monitoring instead of pretending you found an internal cause.

Related skills:
- `test-driven-development`
- `verification-before-completion`
