# Test session 3 — skills

_Captured from the Claude Code session (Practice: on-demand skills)._

```
> Review the application files in PR #2 from danielciolfi/pr-review-practice for style issues.

⏺ github - get_pull_request (MCP)(owner: "danielciolfi", repo: "pr-review-practice", pullNumber: 2)
  ⎿  PR #2 "Add profile lookup" — src/profile_service.py (+9 −0)

⏺ The changed file isn't under tests/ and isn't named test_*.py, so I pulled in
  app-conventions; test-conventions stays out.

⏺ Skill(app-conventions)
  ⎿  Read SKILL.md — 3 rules (naming, type hints/docstrings, error handling)

⏺ src/profile_service.py
  [LOW] `loading` should read as `is_loading` — naming convention.
  [MEDIUM] `FetchProfile` should be snake_case — naming convention.
  [LOW] `FetchProfile` has no type hints or docstring.
  [MEDIUM] `tags=[]` is a mutable default argument.

> Review the test files in PR #4 from danielciolfi/pr-review-practice for style issues.

⏺ github - get_pull_request (MCP)(owner: "danielciolfi", repo: "pr-review-practice", pullNumber: 4)
  ⎿  PR #4 "Add trip list feature" — src/trip_service.py (+7 −0), tests/test_trip_service.py (+10 −0)
     Scoping this review to the test file only, as requested.

⏺ tests/test_trip_service.py is under tests/, so I pulled in test-conventions; app-conventions
  stays out.

⏺ Skill(test-conventions)
  ⎿  Read SKILL.md — 3 rules (naming, fixtures, isolation)

⏺ tests/test_trip_service.py
  [LOW] `test_1` doesn't describe the behavior under test.
  [MEDIUM] Instantiates a real `ApiClient` instead of mocking it.

> /review-pr 1

⏺ Skill(review-pr)
  ⎿  Running the review workflow for PR 1

⏺ github - get_pull_request (MCP)(owner: "danielciolfi", repo: "pr-review-practice", pullNumber: 1)
  ⎿  PR #1 "Add ride history feature" — src/ride_history_service.py (+13 −0), tests/test_ride_history_service.py (+14 −0)

⏺ src/ride_history_service.py — No findings.
  tests/test_ride_history_service.py — No findings.

  ## Summary
  No findings. PR-01 is clean.

  I'm ready to post this review. Should I post it as a comment? Reply `yes` or `post`.

> no

⏺ Understood — I won't post the comment.
```
