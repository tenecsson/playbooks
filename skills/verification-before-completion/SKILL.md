---
name: verification-before-completion
description: Use when you are about to claim something is complete, fixed, or passing and need fresh evidence before saying so
---

Evidence before claims.

Before saying `done`, `fixed`, `passing`, or `ready`:
1. Identify the command that proves the claim.
2. Run that command now.
3. Read the output and exit status.
4. If the output does not prove the claim, report the real status instead.
5. Only then make the claim.

Apply this to:
- tests passing
- lint or build success
- bug fixes
- merge readiness
- subagent completion reports
- requirements completion

Rules:
- Fresh verification only. Old runs do not count.
- Full verification only. Partial checks do not justify broader claims.
- Agent or tool success messages do not count as proof.
- If a claim needs multiple commands, run all of them before making it.
