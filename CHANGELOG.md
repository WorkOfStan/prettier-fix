# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### `Added` for new features

### `Changed` for changes in existing functionality

### `Deprecated` for soon-to-be removed features

### `Removed` for now removed features

### `Fixed` for any bugfixes

### `Security` in case of vulnerabilities

## [1.1.1] - 2025-01-18

### Fixed

- **Checkout code**: Fetches the latest changes so that modifications from a previous job are included, enabling seamless job chaining.

## [1.1.0] - 2024-11-30

### Added

- The input parameter `commit-changes: true` to commit to the current branch.
- **Customizable Commit Message**: Introduced an input `commit-message` to allow users to specify a custom commit message.
- **Branch Name Output**: The `branch-name` is now provided as an output for downstream workflows.
- **Prettier Installation Check**: Ensures `Prettier` is installed and available even if `skip-package-setup` is true.
- Notice about a successful commit.

### Changed

- **Manual Workflow File Change Warnings**: Improved warnings for `.github/workflows/` changes, providing clear guidance without restoring or resetting these files.
- **Cleanup Logic Enhancements**: Enhanced cleanup logic to remove temporary `package.json`, `package-lock.json`, and `node_modules` only when necessary.

## [1.0.3] - 2024-10-20

### Fixed

- Revert changes in .github/workflows/\*.yml before checking other changes, so when only non-editable files should be changed, no new branch is created and the action still gracefully exit 0.

## [1.0.2] - 2024-10-20

### Fixed

- If only changes are in .github/workflows/\*.yml , then the action still should gracefully exit 0.

## [1.0.1] - 2024-10-20

### Changed

- A warning appears in the GitHub Actions Annotations section if changes occur and therefore a new branch is created.
- A proposed manual changed linked from the warning in the GitHub Actions Annotations section.

## [1.0.0] - 2024-08-21

- This GitHub Action automates Prettier formatting across your project, ensuring consistent code styling by creating a new branch for review when necessary. It simplifies integrating Prettier into your workflow, although updates to workflow YAML files in `.github/workflows/` must be done manually.

[Unreleased]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.1...HEAD
[1.1.1]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.0...v1.1.1?w=1
[1.1.0]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.3...v1.1.0?w=1
[1.0.3]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.2...v1.0.3?w=1
[1.0.2]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.1...v1.0.2?w=1
[1.0.1]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.0...v1.0.1?w=1
[1.0.0]: https://github.com/WorkOfStan/prettier-fix/releases/tag/v1.0.0
