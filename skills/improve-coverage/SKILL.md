---
name: improve-coverage
description: Use when the user asks to improve test coverage or uncovered behavior needs a focused coverage pass
---

Increase confidence, not merely the percentage.

1. Get a baseline report when the project supports one. Identify important uncovered behavior, branches, and failure paths.
2. Prioritize by regression risk and user impact. Ignore generated, unreachable, or trivial code unless the user explicitly wants denominator cleanup.
3. Add focused tests through stable boundaries. Prefer plausible inputs and outcomes over mocks, source-text checks, private structure, or assertions copied from the implementation.
4. Run each affected test, then the relevant suite. Check for leaked files, environment changes, globals, timers, or other pollution.
5. Measure the resulting coverage and report meaningful branches covered, remaining risk, and any diminishing returns.

Do not:
- divide work into arbitrary line-count segments
- add tests that cannot fail under a plausible regression
- change production visibility or exclude code solely to improve the number
- preserve a brittle test merely because it increases coverage
- chase a target after the remaining tests cost more than the risk they reduce without telling the user

If a test is disproportionately hard to write, first check whether the boundary is wrong or the uncovered code is worth testing. Do not redesign production solely for coverage without user-visible or correctness value.
