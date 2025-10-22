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

## [1.1.6.2] - 2025-10-23

chore: make the commit message compliant with Conventional Commits

### Changed

- make the commit message compliant with Conventional Commits
- Bump [actions/setup-node](https://github.com/actions/setup-node) from 4 to 6.
  - [Release notes](https://github.com/actions/setup-node/releases)
  - [Commits](https://github.com/actions/setup-node/compare/v4...v6)

## [1.1.6.1] - 2025-09-13

fix: Tags MUST NOT trigger the GitHub Action.

### Fixed

- Trigger changed to ignore tags. I.e. change of the original trigger `on: [pull_request, push]` which caught also tags. (When running on a tag, actions/checkout runs on refs/tags/vX.Y.Z, so you end up with a detached HEAD, and github.head_ref is empty (it only exists on pull_request).)

## [1.1.6] - 2025-09-12

chore: bump GitHub Actions

### Changed

- bump super-linter to v8.1.0
- bump actions/checkout to v5

## [1.1.5] - 2025-06-21

fix: only warn about `.github/workflows/*.yml` issues

### Fixed

- if only `.github/workflows/*.yml` need prettier fix, then end with warning, not with an error

## [1.1.4] - 2025-05-31

chore: outputs `changed-files`

### Added

- outputs `changed-files` with a comma-separated list of files changed by phpcbf
- `prettier-config-path` as an optional path to a custom Prettier config file

### Changed

- list of branches if `debug` is `true`

## [1.1.3] - 2025-03-01

fix: pull request issues

### Added

- debug info

### Fixed

- Prevents issues with changing files in detached HEAD states (during pull request) by committing to the source branch of the pull request.

## [1.1.2] - 2025-02-22

### Added

- notice the commit URL

### Changed

- a more verbose notice about commit

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

[Unreleased]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.6.2...HEAD
[1.1.6.2]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.6.1...v1.1.6.2?w=1
[1.1.6.1]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.6...v1.1.6.1?w=1
[1.1.6]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.5...v1.1.6?w=1
[1.1.5]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.4...v1.1.5?w=1
[1.1.4]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.3...v1.1.4?w=1
[1.1.3]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.2...v1.1.3?w=1
[1.1.2]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.1...v1.1.2?w=1
[1.1.1]: https://github.com/WorkOfStan/prettier-fix/compare/v1.1.0...v1.1.1?w=1
[1.1.0]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.3...v1.1.0?w=1
[1.0.3]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.2...v1.0.3?w=1
[1.0.2]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.1...v1.0.2?w=1
[1.0.1]: https://github.com/WorkOfStan/prettier-fix/compare/v1.0.0...v1.0.1?w=1
[1.0.0]: https://github.com/WorkOfStan/prettier-fix/releases/tag/v1.0.0
