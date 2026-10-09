# AI-Generated Code Review Checklist

Use this checklist before approving or merging a coding-agent change. Mark each item Pass, Fail, or N/A and include evidence for important decisions.

## Specification and scope

- [ ] The change maps to an approved task spec and acceptance criteria.
- [ ] No unrelated refactors, formatting sweeps, or unrequested files were added.
- [ ] Public APIs, schemas, and existing behavior remain compatible or are intentionally versioned.
- [ ] Assumptions and unresolved questions are documented.

## Implementation

- [ ] The implementation is simpler than or equal in complexity to the problem it solves.
- [ ] Inputs are validated at trust boundaries.
- [ ] Error paths are explicit and useful; errors are not silently swallowed.
- [ ] Boundary cases, empty values, duplicates, timeouts, and concurrency are considered where relevant.
- [ ] Resource usage and performance are reasonable for expected scale.
- [ ] No hard-coded credentials, secrets, personal data, or environment-specific paths are present.

## Tests and evidence

- [ ] Tests cover acceptance criteria, not just implementation details.
- [ ] Relevant success, boundary, and failure cases are covered.
- [ ] The reported test commands were actually executed.
- [ ] Failures were investigated rather than hidden or bypassed.
- [ ] Mocks are not being presented as proof of real integration behavior.
- [ ] Lint, type checks, build, or formatting checks were run when relevant, or their omission is explained.

## Security and operations

- [ ] Authorization and authentication behavior has not been weakened.
- [ ] Database queries, shell calls, deserialization, and output rendering are safe for their context.
- [ ] Logging avoids secrets and sensitive payloads.
- [ ] Migrations, feature flags, observability, rollback, and deployment risks are addressed when relevant.
- [ ] Dependencies are necessary, maintained, and compatible with project policy.

## Diff and handoff

- [ ] The complete diff, including untracked files, was reviewed.
- [ ] Generated, vendored, and lock files are handled using the project's normal process.
- [ ] Documentation and examples match the actual behavior.
- [ ] Remaining risks and manual verification steps are explicit.
- [ ] The reviewer has enough evidence to approve the change.

**Decision:** Approve / Request changes / Needs more evidence

**Evidence and follow-up:**
- Tests run:
- Risks:
- Required changes:
