# Troubleshooting

Common questions when using `datafun_toolkit`.

## Why does the log file appear in the project root?

This is intentional.

WHY:
- Makes logs easy to find
- Keeps paths consistent across machines
- Avoids writing to user-specific locations

## Why do logs avoid usernames and full paths?

This toolkit sanitizes paths to protect privacy and keep logs portable.

If a full path is logged directly, the entire machine path may appear.

Example (not recommended):

```python
LOG.info(f"ROOT_PATH = {ROOT_PATH}")
```

Recommended:

```python
log_path(LOG, "ROOT_PATH", ROOT_PATH)
```

WHY:
- Produces repo-relative paths when possible
- Avoids exposing usernames or home directories
- Keeps logs consistent across machines and CI

## Why does detect_shell() return "unknown"?

Shell detection is heuristic.

OBS:
- Some terminals do not expose identifying environment variables.
- In these cases, returning `"unknown"` is expected.

## Does this toolkit collect or transmit data?

No.

OBS:
- All functions run locally.
- No network calls, telemetry, or persistent identifiers are used.
