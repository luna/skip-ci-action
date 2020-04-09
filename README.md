# Skip CI Action
This action allows you to trigger different CI statuses based on the changed
files or commands in commit messages. It can be configured to either output the
status, or trigger the status itself.

## Inputs

### `github-token`
A GitHub authentication token.

- **Optional:** `false`

### `excluded-paths`
A list of paths that should be excluded from CI.

- **Optional:** `true`
- **Default:** `[]`

### `stop-internally`
Whether or not the action should stop the workflow itself.

- **Optional:** `true`
- **Default:** `true`

### `skip-ci-message`
The string in the commit message used to skip the CI run.

- **Optional:** `true`
- **Default:** `[skip ci]`

## Example Usage

```yaml
name: Conditionally Skip CI
uses: luna/skip-ci-action@0.1
with:
    github-token: ${{ github.token }}
    excluded-paths:
    - /doc/*
    - README.md
    stop-internally: true
    skip-ci-message: true
```

