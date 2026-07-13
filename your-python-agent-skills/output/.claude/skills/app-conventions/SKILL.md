---
name: "app-conventions"
description: "Application and library code conventions for the Python team. Load when reviewing non-test Python code — any file that is not under tests/ and not named test_*.py or *_test.py."
---

## Rules

1. **Naming** — Classes are PascalCase; functions and variables are snake_case. A function
   named `FetchProfile` is a violation; it should be `fetch_profile`. Booleans read as a
   question: `is_loading`, `has_session`, `can_retry` — a bare `loading` is a violation. Avoid
   abbreviations except `id`/`url`/`api`/`http`.
2. **Type hints and docstrings** — Public functions and classes have type hints on their
   signatures and a short docstring. A public function with no type hints is a violation.
3. **Error handling** — No bare `except:` — it swallows every error, including
   `KeyboardInterrupt`. No mutable default arguments (for example `def f(items=[])`) — the
   default is shared across calls.

## Template

Compliant:

```python
class ProfileService:
    """Fetches a user profile through the profile repository."""

    def __init__(self, profile_repository: "ProfileRepository") -> None:
        self._profile_repository = profile_repository
        self.is_loading = False

    def fetch_profile(self, user_id: str) -> "Profile":
        self.is_loading = True
        try:
            return self._profile_repository.get(user_id)
        finally:
            self.is_loading = False
```

Non-compliant:

```python
class ProfileService:
    loading = False                             # boolean missing is/has/can

    def FetchProfile(self, user_id, tags=[]):    # should be snake_case; mutable default;
        tags.append("fetched")                   # no type hints or docstring
        return Profile(user_id, tags)
```
