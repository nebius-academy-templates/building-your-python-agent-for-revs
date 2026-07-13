# PR Review Agent — practice project

You are building a PR Review Agent for the Python team. It reviews Python pull requests for
style, security, and architecture issues, organizes findings per file with `[SEVERITY]` tags,
ends with a `## Summary`, and always asks for confirmation before posting a comment to GitHub.

## Files to complete in this task

- `.gitignore` — make sure your GitHub MCP configuration file (the one holding your access
  token) is listed so it is never committed.
- `results/test-session-2.md` — a transcript of the live PR-01 review through the GitHub MCP server and
  the publish-gate test.

> Set up the GitHub MCP server locally as well. That configuration file is **not** committed —
> it stays ignored via `.gitignore`.
