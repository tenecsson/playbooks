---
name: implementation-quality
description: Use when implementing or reviewing code changes that need judgment about proportionate testing and verification
---

Protect meaningful behavior with the cheapest reliable evidence.

Choose the evidence by change type:
- Observed bug or correctness invariant: add a focused regression test when it can fail for the actual defect through a stable boundary.
- Risky logic, async flow, state, resource ownership, security, or compatibility: test plausible outcomes and failure modes.
- Refactor: rely on existing behavior tests; add a test only for a real contract that was previously unprotected.
- Visual tuning, configuration, documentation, generated artifacts, or trivial wiring: prefer build, typecheck, lint, artifact inspection, or a manual check unless a durable automated contract is valuable.
- If the user explicitly says not to add tests, honor that and use permitted non-test verification.

Test quality:
- Test observable behavior or a durable interface, not copied constants, source text, exact private structure, or incidental call order unless that is the explicit contract.
- Prefer realistic construction and public entry points. Avoid prototype-only objects or mocks that permit impossible states.
- A test should fail under a plausible regression. Do not keep one solely because it adds coverage or proves the code you just wrote.
- If the harness is larger than the change, the first failure is setup noise, or the expected value is unclear, reconsider the boundary before proceeding.
- Do not change an expectation merely to match the implementation; derive it from requirements or independent evidence.

For a suitable regression, confirm the test fails for the expected reason, make the smallest coherent fix, then rerun the targeted and relevant surrounding checks. For changes unsuited to a new test, implement directly and verify proportionately.

Before completion, run fresh commands that support the claims you will make. Partial checks support partial claims; summaries from agents or tools are not evidence by themselves. Review new tests as production code and remove redundant or brittle ones.
