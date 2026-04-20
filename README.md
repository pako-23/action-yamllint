[![Latest Release](https://img.shields.io/github/v/release/pako-23/action-yamllint?sort=semver)](https://github.com/pako-23/action-yamllint/releases/latest)
[![Lint YAML](https://github.com/pako-23/action-yamllint/actions/workflows/lint.yaml/badge.svg)](https://github.com/pako-23/action-yamllint/actions/workflows/lint.yaml)

# yamllint GitHub Action

A GitHub Action to lint YAML files using [yamllint].

## Usage

```yaml
- uses: pako-23/action-yamllint@v0
  with:
    files: .
    working_directory: ${{ github.workspace }}
```

## Inputs

| Input | Description | Default |
|-------|-------------|:-------:|
| `files` | Files or directories to check | `.` |
| `working_directory` | The directory where to run yamllint from | `${{ github.workspace }}` |

## Example Workflow

```yaml
name: Lint YAML

on:
  push:
    branches:
      - main
    paths:
      - '**.yaml'
      - '**.yml'
  pull_request:
    paths:
      - '**.yaml'
      - '**.yml'

jobs:
  yamllint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6

      - uses: pako-23/action-yamllint@v0
```

## License

[MIT]

[mit]:
  https://github.com/pako-23/action-yamllint/blob/main/LICENSE
[yamllint]:
  https://yamllint.readthedocs.io/
