# Prettier-Fix

With the release of [Super-Linter](https://github.com/super-linter/super-linter) 7.0.0, [Prettier](https://prettier.io/) has become the standard for many file formats, ensuring consistent code styling across your projects. Embrace this change and keep your codebase looking sharp by integrating Prettier directly into your workflow. While you can still rely on your favorite IDE to apply Prettier's formatting, why not automate the process with this GitHub Action using vanilla Prettier?

### How to Use It

To automate Prettier, simply add [the provided YAML configuration](.github/workflows/prettier-fix.yml) to your repository. If needed, a new branch with a name starting with `prettier/` will be created, making it easy to review and merge the fixes into your main branch.

Note: This action is not blocking, so the status remains green even if changes are proposed in the form of a new branch. It’s up to you to either create a pull request to merge the changes or delete the branch.

### Important Note for Workflow YAMLs

If the changes involve files within the `.github/workflows/` directory, these cannot be done automatically and need to be updated manually.
So, it also checks for any changes made to the `.github/workflows` directory and issues a warning if changes are detected, advising you to manually review and fix these to avoid conflicts with Super-Linter.
After making the necessary adjustments, simply create a pull request to finalize the changes and keep your repository in top shape.
