---
name: "review-pr"
description: "Run the full Python PR review on a single explicit command: /review-pr <number>. Triggered explicitly, not auto-invoked."
disable-model-invocation: true
---

## Steps

1. **Fetch the PR.** Use the GitHub MCP server (`get_pull_request`) to fetch the diff for the
   PR number in `$ARGUMENTS` from `danielciolfi/pr-review-practice`.
2. **Review application files.** For every changed file that is not a test file, apply the
   `app-conventions` skill and record style findings.
3. **Review test files.** For every changed file under `tests/` or matching `test_*.py`, apply
   the `test-conventions` skill and record findings.
4. **Flag security issues.** Scan all changed files for hardcoded API keys, tokens,
   passwords, or secrets, unsafe API usage, and missing input validation. Mark hardcoded
   credentials `[HIGH]`.
5. **Compile findings** into the output format from `CLAUDE.md`: organized per file with
   `[SEVERITY]` tags, ending with a `## Summary` section.
6. **Present and gate.** Show the complete review and ask: "Post this as a comment? Reply
   `yes` or `post`." Post the comment **only** if the user replies `yes` or `post`; otherwise
   do nothing.
