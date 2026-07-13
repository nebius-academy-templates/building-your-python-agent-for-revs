---
name: "review-pr"
description: "Run the full Python PR review on a single explicit command: /review-pr <number>. Triggered explicitly, not auto-invoked."
disable-model-invocation: true
---

## Steps

1. **Fetch the PR.** Use the GitHub MCP server (`get_pull_request`) to fetch the diff for the
   PR number in `$ARGUMENTS` from `danielciolfi/pr-review-practice`.
2. **Delegate to `style-reviewer`.** Pass the diff to the `style-reviewer` sub-agent (it
   applies `app-conventions` to non-test files and `test-conventions` to test files) and
   collect its style findings.
3. **Delegate to `security-reviewer`.** Pass the diff to the `security-reviewer` sub-agent to
   flag hardcoded credentials, unsafe API usage, missing input validation, and insecure
   storage.
4. **Delegate to `architecture-reviewer`.** Pass the diff to the `architecture-reviewer`
   sub-agent to check it against the architecture guidelines.
5. **Consolidate.** Merge the three sub-agents' findings into one review in the `CLAUDE.md`
   output format: organized per file with `[SEVERITY]` tags, ending with a `## Summary`
   section that names the highest severity found.
6. **Present and gate.** Show the consolidated review and ask: "Post this as a comment? Reply
   `yes` or `post`." Post the comment **only** if the user replies `yes` or `post`; otherwise
   do nothing.
