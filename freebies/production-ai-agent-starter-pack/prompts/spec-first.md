# Spec-First Prompt for Coding Agents

Copy the prompt below into your coding assistant. Replace the bracketed context before use.

---

You are helping modify an existing software repository.

## Context

- Repository/product: [name and purpose]
- Relevant files or modules: [paths, if known]
- Runtime and framework: [language, framework, versions]
- Existing test command: [exact command, if known]
- Task: [one concise sentence]

## Your job — specification before code

Do not edit files yet. Inspect the relevant code and produce a task specification with these sections:

### 1. Goal
Describe the user-visible or system-observable outcome. Avoid implementation assumptions unless required.

### 2. Scope
- In scope:
- Explicitly out of scope:
- Public APIs, data contracts, or behavior that must remain compatible:

### 3. Contract
- Inputs and validation:
- Outputs and return values:
- Side effects:
- Error and failure behavior:
- Invariants:
- Performance or resource constraints, if relevant:

### 4. Acceptance criteria
Write numbered, observable criteria. Each criterion must be testable and avoid vague terms such as “works well”.

### 5. Edge cases
Include empty, malformed, boundary, duplicate, missing, concurrent, timeout, or permission cases when relevant to this task. Do not include irrelevant cases just to fill a list.

### 6. Test plan
For each acceptance criterion, name the unit, integration, contract, or end-to-end test that would verify it. Identify fixtures and mocks, and explain what must be tested against a real dependency.

### 7. Change plan
List the likely files to inspect or change, dependencies that may be added, and any migration, observability, rollout, or rollback considerations.

### 8. Risks and open questions
Separate known facts from assumptions. Ask only questions that block a correct implementation.

## Constraints

- Do not invent repository structure, API behavior, test results, or product requirements.
- Follow the repository's existing patterns and instructions.
- Prefer the smallest design that satisfies the acceptance criteria.
- If the task can be completed in small increments, aim for 50 or fewer changed lines per increment. If that is impractical, explain why.
- Treat this as a review draft, not approval to implement.

Finish with a concise checklist of decisions needed from me. Wait for approval before editing files.
