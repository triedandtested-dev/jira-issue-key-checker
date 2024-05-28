# Jira Issue Key Checker action

Checks If a PR contains its linked Jira issue key in both the title and the description.

### Inputs.
  > **Required**:
  > - GITHUB_TOKEN - DBT cloud api token.
  > - jira-prefix  - The Jira issue key prefix. Ex. ABC-1111, prefix would be ABC.

### Example usage.
```yaml
on:
  pull_request:
    types:
      - opened
      - edited
      - synchronize

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: triedandtested-dev/jira-issue-key-checker@v1.0.0
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          jira-prefix: 'ABC'
```