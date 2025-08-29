# Python - Poetry install GitHub Action

This repository provides a reusable GitHub Action for setting up Python and Poetry and installing and caching your project's Poetry dependencies.

## Usage

To use the action, add it to a workflow in your repository:

```yml
name: Build Python project

on:
  workflow_dispatch:
  pull_request:
  push:
    branches:
      - main

jobs:
  build-python:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v5

      - name: Install Python and dependencies
        uses: minvws/action-python-poetry-install@v1
        with:
          python_version: <python_version>
```

Replace `<python_version>` with the Python version your project needs.

In this basic example, the workflow is executed automatically on push to the `main` branch and on any pull request. And thanks to the `workflow_dispatch` trigger it can also be executed manually from the repository's Actions tab.

### Configuration

The action has the following inputs:

- `python_version`: which version of Python to use. For example `"3.11"` or `">=3.9 <3.14"`.

## Contributing

If you want to contribute a new pipeline, please check the reusable workflow guidelines in the
[GitHub documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows#creating-a-reusable-workflow).

## License

This repository is released under the EUPL 1.2 license. See [LICENSE](./LICENSE) for details.

## Part of iCore

This package is part of the iCore project.
