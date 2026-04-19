# yamllint GitHub Action

A GitHub Action to lint YAML files using [yamllint](https://yamllint.readthedocs.io/).

## Usage

```yaml
- uses: pako-23/action-yamllint@v1
  with:
    files: .
    working_directory: ${{ github.workspace }}
```

## Inputs

| Input | Description | Default |
|-------|-------------|---------|
| `files` | Files or directories to check | `.` |
| `working_directory` | The directory where to run yamllint from | `${{ github.workspace }}` |

## Example Workflow

```yaml
name: Lint YAML

on: [push, pull_request]

jobs:
  yamllint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: pako-23/action-yamllint@v1
        with:
          files: .
```

## License

[MIT]

[mit]:
  https://github.com/pako-23/action-yamllint/blob/main/LICENSE
