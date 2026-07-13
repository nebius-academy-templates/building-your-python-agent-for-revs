# PR Review Agent — practice project

You are building a PR Review Agent for the Python team. It reviews Python pull requests for
style, security, and architecture issues, organizes findings per file with `[SEVERITY]` tags,
ends with a `## Summary`, and always asks for confirmation before posting a comment to GitHub.

## Files to complete in this task

- `.claude/skills/app-conventions/SKILL.md` — knowledge skill that loads for application code.
- `.claude/skills/test-conventions/SKILL.md` — knowledge skill that loads for test code.
- `.claude/skills/review-pr/SKILL.md` — workflow skill that runs the full review on one command.
- `results/test-session-3.md` — a transcript showing selective skill loading and the workflow run.
