---
name: "test-conventions"
description: "Test code conventions for the Python team. Load when reviewing test code — files under tests/, files matching test_*.py or *_test.py, or files that import pytest."
---

## Rules

1. **Naming** `[LOW]` — Test function names start with `test_` and describe the behavior
   under test, not just the function being tested. `def test_1():` is a violation; prefer
   `def test_load_trips_returns_recent_trips():`.
2. **Fixtures** `[LOW]` — Prefer a pytest fixture over duplicating setup code across tests.
   Copy-pasted setup in every test function is a violation.
3. **Isolation** `[MEDIUM]`/`[HIGH]` — A test must not call a real network, database, or
   filesystem endpoint; mock it instead — `[MEDIUM]`. A test whose outcome depends on another
   test's side effects or on run order is a violation — `[HIGH]`.

## Template

Compliant:

```python
import pytest
from unittest.mock import Mock

from src.trip_service import TripService


@pytest.fixture
def api_client() -> Mock:
    return Mock()


def test_load_trips_returns_trips_from_the_api_client(api_client: Mock) -> None:
    api_client.get.return_value = ["trip-1"]
    service = TripService(api_client)

    trips = service.load_trips(42)

    assert trips == ["trip-1"]
```

Non-compliant:

```python
from src.api_client import ApiClient
from src.trip_service import TripService


def test_1():                                  # name doesn't describe the behavior
    service = TripService(ApiClient())          # hits a real client instead of mocking it
    result = service.load_trips(42)
    assert result is not None
```
