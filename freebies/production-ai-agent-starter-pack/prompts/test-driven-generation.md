# Test-Driven Generation Prompt

Use this after the task specification is reviewed and approved.

---

Implement the approved specification in this repository. Follow repository instructions and existing conventions.

## Phase 1 — Tests first

1. Re-read the approved acceptance criteria and relevant code.
2. Identify the actual test framework and commands from repository configuration; do not guess.
3. Add or update focused tests for the acceptance criteria before changing production behavior.
4. Include relevant happy paths, boundaries, and failure cases.
5. Run the new tests before implementation when feasible. Record the actual failing output; do not fabricate a red test if the environment cannot run it.

## Phase 2 — Minimal implementation

1. Implement only what is needed to satisfy the spec and tests.
2. Work in small, reviewable increments. Aim for 50 or fewer changed lines per increment; explain and request approval if a larger indivisible change is necessary.
3. Avoid unrelated refactors, new dependencies, and broad formatting.
4. Do not disable, weaken, or delete a meaningful test just to obtain a pass.
5. If the spec conflicts with existing behavior or repository instructions, stop and explain the conflict.

## Phase 3 — Verification

Run the relevant tests after implementation, then appropriate lint, type, build, or formatting checks if available.

For every command, report:
- Exact command executed.
- Whether it completed.
- Pass/fail and the meaningful result.
- Any test skipped and the reason.

Do not claim success for checks that were not run. Distinguish unit tests from integration tests and mocked behavior from real dependency behavior.

## Phase 4 — Review handoff

Inspect the complete diff, including untracked files. Check for:
- Changes outside the approved scope.
- Secrets, credentials, and sensitive data.
- Unhandled errors and missing edge cases.
- API or schema compatibility issues.
- New dependencies or generated files.
- Missing tests or undocumented assumptions.

Return a concise summary of the implementation, test evidence, remaining risks, and files changed. Do not commit, push, merge, deploy, or publish unless explicitly authorized.
