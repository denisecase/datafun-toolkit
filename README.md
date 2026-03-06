# Data Analytics Fundamentals: Toolkit

[![PyPI version](https://img.shields.io/pypi/v/datafun-toolkit)](https://pypi.org/project/datafun-toolkit/)
[![Latest Release](https://img.shields.io/github/v/release/denisecase/datafun-toolkit)](https://github.com/denisecase/datafun-toolkit/releases)
[![Docs](https://img.shields.io/badge/docs-live-blue)](https://denisecase.github.io/datafun-toolkit/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/license/MIT)
[![CI](https://github.com/denisecase/datafun-toolkit/actions/workflows/ci-python-zensical.toml/badge.svg?branch=main)](https://github.com/denisecase/datafun-toolkit/actions/workflows/ci-python-zensical.toml)
[![Deploy-Docs](https://github.com/denisecase/datafun-toolkit/actions/workflows/deploy-zensical.toml/badge.svg?branch=main)](https://github.com/denisecase/datafun-toolkit/actions/workflows/deploy-zensical.toml)
[![Check Links](https://github.com/denisecase/datafun-toolkit/actions/workflows/links.yml/badge.svg)](https://github.com/denisecase/datafun-toolkit/actions/workflows/links.yml)
[![Dependabot](https://img.shields.io/badge/Dependabot-enabled-brightgreen.svg)](https://github.com/denisecase/datafun-toolkit/security)

> Privacy-safe diagnostics, paths, and logging helpers for analytics projects.

## What This Provides

- `find_project_root()` and `safe_relpath_str()` for robust, repo-relative paths
- `get_logger()` for consistent console and file logging (using a standard logging API)
- `log_header()` for a privacy-safe logging header (shows OS, shell, Python version, repo-relative cwd)

This toolkit is designed for reuse.
It works the same locally and in GitHub Actions.

## Install (Choose One)

```shell
uv add datafun-toolkit
```

```shell
pip install datafun-toolkit
```

## Example

```python

import logging
from pathlib import Path
from datafun_toolkit.logger import get_logger, log_header

LOG: logging.Logger = get_logger("P01", level="DEBUG")

ROOT_PATH: Path = Path.cwd()
DATA_PATH: Path = ROOT_PATH / "data"

def main() -> None:
    """Start the main logic."""
    log_header(LOG, "P01 Pipeline")

    LOG.info("START main()")
    LOG.info(f"ROOT_PATH = {ROOT_PATH}")
    LOG.info(f"DATA_PATH = {DATA_PATH}")
    LOG.info("Working....")

    LOG.info("END main()")


# === CONDITIONAL EXECUTION GUARD ===

if __name__ == "__main__":
    main()

```

## Developer Setup

Install tools:

- git
- uv
- VS Code

One-time setup:

```shell
uv self update
uv python pin 3.14
uv sync --extra dev --extra docs --upgrade

uvx pre-commit install
git add -A
uvx pre-commit run --all-files
```

Before starting work:

```shell
git pull
```

After working, run checks:

```shell
uv run ruff format .
uv run ruff check . --fix
uv run pytest --cov=src --cov-report=term-missing

uv run deptry .
uv run bandit -c pyproject.toml -r src
uv run validate-pyproject pyproject.toml
```

Build and serve docs:

```shell
uv run zensical build
uv run zensical serve
```

Hit **CTRL+c** in the VS Code terminal to quit serving.

Save progress frequently (some tools may make changes; you may need to **re-run git `add` and `commit`** to ensure everything gets committed before pushing):

```shell
git add -A
git commit -m "update"
git push -u origin main
```

## Annotations

[ANNOTATIONS.md](./ANNOTATIONS.md)

## Citation

[CITATION.cff](./CITATION.cff)

## License

[MIT](./LICENSE)

## SE Manifest

[SE_MANIFEST.md](./SE_MANIFEST.toml)
