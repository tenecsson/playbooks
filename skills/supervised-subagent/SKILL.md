---
name: supervised-subagent
description: Use when the user asks to delegate implementation to a subagent
---


Use one child for implementation and revisions while the parent owns acceptance.

Workflow:
1. Spawn the child with a bounded task, acceptance criteria, relevant constraints, and proportionate verification. Honor the user's model and reasoning-effort choices; otherwise use the environment's defaults.
2. Tell the child to message the parent only when blocked or when an implementation or revision pass is complete. Do not request routine progress reports.
3. The parent may perform useful independent work. When none remains, call `wait_agent` with `timeout_ms: 1200000`, capped by tool limits and higher-priority instructions. Treat the wait as event-driven: it returns early for a child message or new user input. Do not shorten it merely to provide periodic updates.
4. After each completed pass, inspect the actual changes and run proportionate verification. Do not accept the child's summary as sufficient evidence.
   - Do not automatically require new tests or strict test-first sequencing.
   - Every new test should protect a plausible regression or durable contract. Reject tests that merely mirror constants, match source text, freeze private structure, or construct impossible internal states unless that is explicitly the required contract.
   - Honor user instructions to skip tests, worktrees, commits, documentation, or other process.
5. If changes are needed, send one consolidated, actionable revision request to the same child, then use the same wait. Repeat until material requirements and risks are addressed or a genuine blocker requires user input. Do not add rounds for speculative polish or assertion count.

Polling rules:
- Do not replace `wait_agent` with shell sleeps or another polling loop.
- Before a timeout, do not call `list_agents` or send progress nudges.
- After the first timeout, call `list_agents` once. If the child is active, give at most one concise user update and wait another interval without nudging.
- Send a nudge only after a second consecutive timeout or evidence of inconsistent or stalled state.

Report the accepted result, material review corrections, and verification evidence. If blocked, report the unresolved requirement and the input needed to continue.
