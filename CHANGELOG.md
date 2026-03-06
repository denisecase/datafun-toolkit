# Changelog

All notable changes to this project will be documented in this file.

The format is based on **[Keep a Changelog](https://keepachangelog.com/en/1.1.0/)**
and this project adheres to **[Semantic Versioning](https://semver.org/spec/v2.0.0.html)**.

## [Unreleased]

---

## [1.0.0] - 2026-03-06

### Updated

- Declared stable public API
- Updated documentation and examples
- Standardized privacy-safe path logging with `log_path()`

---

## [0.9.6] - 2026-03-06

### Updated

- Documentation system migrated from MkDocs to Zensical
- Default logging behavior uses sanitized relative paths

---

## [0.9.5] - 2026-01-11

### Updated

- Updated with improved configs

---

## [0.9.4] - 2026-01-08

### Updated

- Updated with improved ci/cd

---

## [0.9.3] - 2026-01-02

### Updated

- Minor revisions

---

## [0.9.2] - 2026-01-02

### Updated

- Minor revisions

---

## [0.9.1] - 2026-01-02

### Added

- Initial public release
- Docs site scaffolding (MkDocs Material, i18n)
- Testing: Ruff lint; pre-commit hooks
- Packaging
- Privacy-first design
- CI/CD: GitHub Actions for checks, docs, and automated releases

---

## Notes on versioning and releases

- We use **SemVer**:
  - **MAJOR** – breaking schema/OpenAPI changes
  - **MINOR** – backward-compatible additions
  - **PATCH** – clarifications, docs, tooling
- Versions are driven by git tags via `setuptools_scm`. Tag `vX.Y.Z` to release.
- Docs are deployed per version tag and aliased to **latest**.
- Sample commands:

```shell
git tag -d v1.0.0
git push origin :refs/tags/v1.0.0

git tag v1.0.0 -m "1.0.0"
git push origin v1.0.0
```

[Unreleased]: https://github.com/denisecase/datafun-toolkit/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/denisecase/datafun-toolkit/releases/tag/v1.0.0
[0.9.6]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.6
[0.9.5]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.5
[0.9.4]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.4
[0.9.3]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.3
[0.9.2]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.2
[0.9.1]: https://github.com/denisecase/datafun-toolkit/releases/tag/v0.9.1
