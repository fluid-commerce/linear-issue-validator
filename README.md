# Linear Issue Validator

A GitHub Action that validates whether a Linear issue reference (e.g., LINEAR-123) is present in either the branch name or pull request description.

## Dependencies

This action requires that the [Linear GitHub Integration](https://linear.app/docs/github) is already installed on your repository.

## Usage

```yaml
name: Linear Issue Validation

on:
  pull_request:
    types: [opened, edited, synchronize, reopened]
  issue_comment:
    types: [created, edited, deleted]

jobs:
  validate-linear-issue:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Validate Linear issue reference
        uses: fluid-commerce/linear-issue-validator@main
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| Input           | Description                                            | Required | Default |
| --------------- | ------------------------------------------------------ | -------- | ------- |
| `github-token`  | GitHub token for API access                            | Yes      | N/A     |

## License

This project is licensed under the [MIT License](LICENSE).
