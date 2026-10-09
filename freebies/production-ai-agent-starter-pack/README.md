# The Production AI Agent Starter Pack

A copy-paste starter kit for using coding agents with smaller, reviewable changes and tests tied to a written specification.

**Audience:** software engineers, AI builders, and technical founders  
**Includes:** agent instruction files, a spec-first prompt, a test-first implementation prompt, a task-spec JSON Schema, a code-review checklist, and platform notes.

## Quick start

1. Choose the instruction file that matches your tool:
   - `templates/AGENTS.md` for tools that read `AGENTS.md`.
   - `templates/CLAUDE.md` for Claude Code projects that use `CLAUDE.md`.
2. Copy it to the appropriate location in your repository and adapt the project-specific commands, test runner, and architecture notes.
3. For a non-trivial task, fill in `schemas/task-spec.schema.json` or use `prompts/spec-first.md` to write a spec first.
4. Ask the agent to propose a small plan and tests before implementation.
5. Implement in small diffs. Review the diff and run the repository's real test and lint commands before accepting changes.

## Pack contents

- `templates/AGENTS.md` — reusable cross-tool repository rules.
- `templates/CLAUDE.md` — Claude Code-oriented version of the rules.
- `prompts/spec-first.md` — turns a request into an explicit, reviewable task spec.
- `prompts/test-driven-generation.md` — asks for tests before production implementation.
- `schemas/task-spec.schema.json` — machine-readable task-spec shape.
- `checklists/ai-code-review.md` — review checklist for agent-generated diffs.
- `COMPATIBILITY.md` — how to adapt the files for Claude Code, Cursor, and Antigravity.

## Important defaults

- The 50 changed-line limit is a **review heuristic**, not a security boundary or a universal platform-enforced limit. If a task needs more, split it or explain why and ask for approval before proceeding.
- Tests must be meaningful and run with the project's actual commands. Never claim tests passed unless they were executed.
- Do not fabricate test output, repository facts, links, benchmark results, or tool capabilities.
- Do not put secrets, tokens, private customer data, or production credentials in prompts or generated files.
- Review generated changes before merging, deploying, or publishing.

## Suggested workflow

`request → spec → plan → tests → small implementation diff → review → verification`

This kit improves consistency; it does not guarantee correct code. Keep normal code review, CI, access controls, and security checks in place.

## License and reuse

Adapt these templates to your project. Before publishing a modified copy, retain any repository-level license and attribution requirements that apply.
