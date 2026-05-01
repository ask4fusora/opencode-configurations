---
name: write-conventional-commit-message
---

## Objective

Analyze code changes and produce a commit message following the **Conventional Commits v1.0.0**
specification.

## Rules

- Describe what changed and why. If the diff is ambiguous or incomplete, describe only the visible
  changes (what).
- Prefer header-only if sufficient. Only include body for additional context.
- Limit header to 72 chars (prevents GitHub truncation); hard wrap body at 72 chars (readability).
- Brief and concise.
- Omit implementation details.
- Use full terminology (e.g., `authentication`, not `auth`).
- Wrap code references (paths, variables) in backticks.

## Output Format

Use this template:

```
<type>[optional scope]: <description>

[Optional body]

[Optional footer(s)]
```

### Syntax and Structure

- `type`: Lowercase noun. Prefer standard types; use custom if more precise.
- `scope`: Include scope if single; else omit.
- `description`: Complete the sentence: "If applied, this commit will \<description\>."
- Breaking change: prepend `!` before colon (e.g., `feat(api)!: remove v1 endpoints`) and include
  `BREAKING CHANGE:` footer.

### Type Reference

- **Standard**: `feat` (new feature), `fix` (bug fix), `docs` (documentation), `style` (formatting),
  `refactor` (no bug fix/feature), `perf` (performance), `test` (tests), `build` (build
  system/deps), `ci` (CI config/scripts), `chore` (other), `revert` (revert commit).
- **Custom**: Create specific types (e.g., `security`, `deps`, `config`, `i18n`, `types`) for better
  semantic clarity.

## Examples

### Example 1: Standard Feature

```
feat(lang): add polish language support
```

### Example 2: Custom Type

```
security: patch sql injection vulnerability in login query
```

### Example 3: Breaking Change

```
feat(authentication)!: switch to OAuth2 provider

BREAKING CHANGE: The Basic Auth implementation has been removed.
Clients must now authenticate using the `/oauth/token` endpoint.
```
