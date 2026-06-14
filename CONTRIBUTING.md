# The Dipshit Labs Contribution Guide

This document covers the exact conventions used across our projects. Follow these rules or prepare to have your Pull Requests closed without review.

## Quick Start

1. Clone the repository.
2. Create a branch matching our naming conventions (see [Branch Naming](#branch-naming)).
3. Write your code, make your commits, and ensure the local linter passes.
4. Open a Pull Request (PR) directly to the `main` branch.

## Branch Naming

Follow [Conventional Branch](https://github.com/nickshanks347/conventional-branch) naming:

```
<type>/<short-hyphenated-description>
```

| Type | Use Case | Example |
|------|----------|---------|
| `feat/`, `feature/` | New functionality that actually does something | `feat/jwt-auth-middleware` |
| `fix/`, `bugfix/` | Fixing code you or someone else broke | `fix/null-pointer-login` |
| `chore/` | Updating dependencies, configuration, or tooling | `chore/bump-nextjs` |
| `docs/` | Updating documentation because you hate writing code | `docs/api-endpoints` |
| `refactor/` | Restructuring code without changing its behavior | `refactor/clean-spaghetti` |
| `ci/` | Changing GitHub Actions because the pipeline broke | `ci/fix-linter-gate` |

Rules:

* Lowercase only.
* No underscores (_). Use hyphens (-).
* Keep it concise. We do not need an essay in the branch name.

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Approved Types:**

* `feat`: A new feature for the user or system.
* `fix`: A bug fix.
* `docs`: Documentation changes only.
* `style`: Changes that do not affect the meaning of the code (formatting, missing semi-colons).
* `refactor`: A code change that neither fixes a bug nor adds a feature.
* `chore`: Updating build tasks, package manager configs, etc.

**Examples:**

```
feat: add embedding generation pipeline
fix(api): handle rate limit errors gracefully
docs: update README with setup instructions
chore(deps): bump transformers to 4.40.0
```

### Breaking Changes

If your code changes an existing API endpoint or database schema in a way that breaks backwards compatibility, add a ! after the type:

```
feat!: redesign model configuration API

BREAKING CHANGE: ModelConfig now requires a `provider` field.
```

## Pull Requests

Before you hit that green button, do a quick sanity check:

- Keep PRs focused on a single concern
- Include tests for new behavior
- Ensure CI passes
- Reference related issues in the PR description
- Follow the PR template when opening a PR
