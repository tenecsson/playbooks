---
name: systematic-debugging
description: Use when any bug, failing test, build break, or unexpected behavior needs root-cause analysis before fixes
---

Find evidence for the cause before committing to a fix.

1. Observe the actual failure. Reproduce it when feasible and inspect the relevant state, logs, recent changes, and boundaries.
2. Trace the bad value or transition toward its source. Compare with a working path when that will discriminate causes.
3. Form one concrete hypothesis and run the smallest useful experiment. Do not stack speculative fixes.
4. Fix the root cause and run verification that exercises the observed failure and nearby behavior.

Use judgment:
- A minimal diagnostic or safe reversible fix may be the fastest experiment; do not turn investigation into ceremony.
- Add a regression test only when it protects a plausible recurrence through a stable boundary. A reproduction script, targeted command, or manual check may be better for visual, environmental, or integration failures.
- For async failures, wait on the relevant condition unless timing is the behavior under test.
- Add validation where it establishes a useful contract, not automatically at every layer.
- Reassess the architecture or ask the user when evidence stops producing progress; there is no fixed attempt count.

Avoid unrelated cleanup. If the cause is external or environmental, report that evidence and add handling or monitoring only when it is in scope.
