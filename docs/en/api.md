# API Reference

Public functions provided by `datafun_toolkit`.

## datafun_toolkit.paths

Utilities for locating the project root and sanitizing paths.

### find_project_root(start: Path | None = None) -> Path

Return the project root directory.

The root is the nearest parent directory containing:

- `pyproject.toml`, or
- `.git`

Example:

```python
from datafun_toolkit.paths import find_project_root

root = find_project_root()
```

### safe_relpath_str(path: Path, root: Path) -> str

Return a repo-relative string for a path when possible.

If the path cannot be made relative to the project root, the filename is returned.

## datafun_toolkit.diagnostics

Environment detection helpers.

### detect_shell() -> str

Return the active shell name when detectable.

Possible values include:

- `pwsh`
- `powershell`
- `bash`
- `zsh`
- `unknown`

### detect_os() -> str

Return a concise operating system description.

Example:

```
Windows 11
Linux 6.6
Darwin 23
```

### detect_python() -> str

Return the active Python version string.

## datafun_toolkit.logger

Logging helpers.

### get_logger(project_name: str, \*, level: str = "INFO") -> logging.Logger

Return a configured logger that writes to console and a log file.

### log_header(logger: logging.Logger, project_name: str) -> None

Emit a standardized run header with environment details.

### log_path(logger: logging.Logger, label: str, path: Path) -> None

Log a repo-relative path in a privacy-safe way.

## Type Hint Support

This package includes a `py.typed` marker file (PEP 561), enabling type checkers such as Pyright to trust inline type hints.
