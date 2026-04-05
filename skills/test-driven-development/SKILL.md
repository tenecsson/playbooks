---
name: test-driven-development
description: Use when implementing any feature, bugfix, refactor, or behavior change before writing production code
---

No production code without a failing test first.

If you already wrote production code, delete or ignore it and restart from the test. Tests written after the fact are verification, not TDD.

Cycle:
1. RED
   - write one minimal test for one behavior
   - make the test name describe behavior clearly
   - prefer real behavior over mocks
2. VERIFY RED
   - run the test
   - confirm it fails for the expected reason, not because of typos or setup noise
3. GREEN
   - write the smallest production change that makes the test pass
   - do not add extra features, abstractions, or cleanup yet
4. VERIFY GREEN
   - rerun the targeted test
   - rerun the relevant surrounding verification
5. REFACTOR
   - clean up only while tests remain green
6. REPEAT

Rules:
- Bug fixes require a failing regression test first.
- If a test is hard to write, the design is probably too hard to use. Simplify the interface.
- Mocks are a last resort, not the default.
- No exceptions without explicit user permission.
