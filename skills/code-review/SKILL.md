---
name: code-review
description: Use when the user requests code review, review feedback must be evaluated, or a high-risk change warrants an independent technical pass
---

Review the actual change against its requirements and risks. Do not add a review round merely because implementation occurred.

Requesting or performing review:
- Use an independent reviewer only when explicitly requested or justified by novelty, uncertainty, blast radius, security, compatibility, or merge risk.
- Inspect the diff and surrounding code; do not trust implementation summaries.
- Prioritize correctness, missing requirements, data loss, races, security, compatibility, and operational failure. Distinguish blocking findings from optional polish.
- Review tests for value: each new test should protect a plausible regression or durable contract. Flag tautological, source-text, private-structure, impossible-state, redundant, and overly mocked tests.
- Cite concrete locations and explain impact and the smallest appropriate correction.

Receiving review:
- Read the complete feedback and verify claims against the codebase and constraints.
- Implement valid findings, consolidate related fixes and verification, and push back with evidence when feedback is wrong or out of scope.
- Ask the user only when ambiguity would materially change the result. Do not serialize every comment into a separate approval or test cycle.

Stop when material requirements and risks are addressed with proportionate evidence. Do not manufacture further rounds for speculative improvements or exact stylistic conformity.
