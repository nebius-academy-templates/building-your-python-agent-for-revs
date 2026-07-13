# PR Review Agent — practice project

You are building a PR Review Agent for the Python team. It reviews Python pull requests for
style, security, and architecture issues, organizes findings per file with `[SEVERITY]` tags,
ends with a `## Summary`, and always asks for confirmation before posting a comment to GitHub.

## Files to complete in this task

- `CLAUDE.md` — add the episodic-memory rule to **Guardrails**: append one line to
  `review_history.md` after every completed review.
- `review_history.md` — the append-only episodic log (at least three entries).
- `.claude/agents/architecture-reviewer.md` — add the semantic-memory step: search `docs/adr/`
  with Grep and cite the matching ADR.

> The ADR knowledge base under `docs/adr/` is already provided for the agent to search.
>
> To confirm semantic memory works, run `/review-pr 4` — the architecture finding should cite
> ADR-003. You do not need to upload this run, so it won't overwrite the
> `results/test-session-4.md` you submitted earlier.
