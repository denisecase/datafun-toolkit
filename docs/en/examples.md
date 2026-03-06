# Examples

Typical usage patterns for the DataFun Toolkit.

## Example: Logging a Run Header

```python
from datafun_toolkit.logger import get_logger, log_header

logger = get_logger("datafun-project", level="INFO")
log_header(logger, "datafun-project")

logger.info("Starting analysis...")
```

Example output:

```
=== RUN START ===
project=datafun-project
repo_dir=datafun-project
python=3.14.1
os=Windows 11
shell=pwsh
cwd=src
github_actions=False
```

## Example: Logging Paths Safely

```python
from pathlib import Path
from datafun_toolkit.logger import get_logger, log_path

logger = get_logger("datafun-project")

ROOT_PATH = Path.cwd()
DATA_PATH = ROOT_PATH / "data"

log_path(logger, "ROOT_PATH", ROOT_PATH)
log_path(logger, "DATA_PATH", DATA_PATH)
```

Example output:

```
ROOT_PATH = .
DATA_PATH = data
```

## Example: Environment Diagnostics

```python
from datafun_toolkit.diagnostics import detect_shell, detect_os, detect_python

print(detect_shell())
print(detect_os())
print(detect_python())
```

Example output:

```
pwsh
Windows 11
3.14.1
```
