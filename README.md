# Prettier-Fix

With the release of [Super-Linter](https://github.com/super-linter/super-linter) 7.0.0, [Prettier](https://prettier.io/) has become the standard for many file formats, ensuring consistent code styling across your projects. Embrace this change and keep your codebase looking sharp by integrating Prettier directly into your workflow. While you can still rely on your favorite IDE to apply Prettier's formatting, why not automate the process with this GitHub Action using vanilla Prettier?

<p align="center">
  <img src=".github/images/social-preview.png" width="128" alt="accessibility text">
</p>

## Features

- Automatically formats code using Prettier.
- Creates a new branch (prefixed with `prettier/`) if changes are required, making it easy to review and merge.
- Allows for customizable commit messages via the `commit-message` input.
- Provides the branch name as an output for downstream workflows.
- Issues warnings for manual changes needed in `.github/workflows` files.

## How to Use It

To automate Prettier, simply add [the provided YAML configuration](.github/workflows/prettier-fix.yml) to your repository.
If needed, by default, a new branch with a name starting with `prettier/` will be created, making it easy to review and merge the fixes into your main branch.
You can however set the input parameter `commit-changes: true` to commit to the current branch.

Note: This action is not blocking, so the status remains green even if changes are proposed in the form of a new branch. It’s up to you to either create a pull request to merge the changes or delete the branch.

### Inputs

| Input                | Description                                                                 | Default                    |
|----------------------|-----------------------------------------------------------------------------|----------------------------|
| `node-version`       | Node.js version to use                                                     | `"20"`                     |
| `commit-changes`     | If `true`, commits changes to the current branch instead of creating a new one | `false`                    |
| `git-user-name`      | Git user name for commits                                                  | `"github-actions[bot]"`   |
| `git-user-email`     | Git user email for commits                                                 | `"github-actions[bot]@users.noreply.github.com"` |
| `skip-package-setup` | If `true`, skips `npm init` and dependency installation steps               | `false`                    |
| `commit-message`     | Commit message for the changes                                             | `"Prettier fixes applied automatically"` |

### Outputs

| Output         | Description                           |
|----------------|---------------------------------------|
| `branch-name`  | The name of the branch created/used   |

## Important Note for Workflow YAMLs

If the changes involve files within the `.github/workflows/` directory, these cannot be done automatically and need to be updated manually.
So, it also checks for any changes made to the `.github/workflows` directory and issues a warning if changes are detected, advising you to manually review and fix these to avoid conflicts with Super-Linter.
After making the necessary adjustments, simply create a pull request to finalize the changes and keep your repository in top shape.
