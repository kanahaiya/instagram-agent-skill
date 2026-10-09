# Platform Compatibility Notes

These files are plain Markdown templates and prompts. A platform's ability to automatically discover a particular instruction file depends on its current configuration and version; do not assume all tools load the same filenames.

## Claude Code

- Place or adapt `CLAUDE.md` at the project root for project instructions.
- Review the current Claude Code documentation for supported instruction-file locations and precedence.
- Treat slash commands, skills, and project instructions as distinct mechanisms: a Markdown prompt is not automatically a registered slash command.

## Cursor

- Cursor projects may use `.cursor/rules/` and supported rule-file formats.
- Adapt the rules in `templates/AGENTS.md` into the rule mechanism configured for your Cursor version.
- Do not assume a root `AGENTS.md` is automatically loaded unless your current setup supports it.

## Google Antigravity

- Workspace skills/instructions depend on the Antigravity version and project setup. In this repository, workspace skills live under `.agents/skills/`; that does not mean every Markdown file in this starter pack is itself a skill.
- Copy relevant rules into the instruction mechanism your Antigravity setup actually loads, or paste the relevant prompt into the agent conversation.
- Test discovery and behavior in the interactive UI before relying on automatic invocation.

## Portable use

When uncertain, paste the relevant prompt explicitly into the agent chat, provide the repository context, and ask it to report which instructions it actually read. Verify the response against the current platform documentation and your own test results.
