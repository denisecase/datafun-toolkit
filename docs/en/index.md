# DataFun Toolkit

The **DataFun Toolkit** provides privacy-safe utilities for analytics Python projects.

This package is designed to be:

- Imported, not modified
- Safe to log and share
- Consistent across operating systems

It helps:

- Locate the project root
- Sanitize file paths for logs
- Detect runtime environment details (OS, shell, Python)
- Emit standardized log headers

## Who This Is For

- Data analysts working on Python projects
- Developers debugging workflows
- Analytics projects needing lightweight diagnostics
- CI / GitHub Actions environments

This toolkit intentionally avoids:

- Heavy dependencies
- Framework assumptions
- User-specific identifiers

## Design Principles

- CI-friendly: behaves the same locally and in GitHub Actions
- Privacy-safe: avoids usernames, hostnames, and absolute home paths
- Teaching-first: clear structure, readable output, predictable behavior
- Industry-legible: follows standard Python logging and packaging practices

## Installation

pip install datafun-toolkit

Or with uv:

    uv add datafun-toolkit
    uv sync

See the API reference for available modules.

## Documentation

- API Reference
- Examples
- Troubleshooting
