# Python - Poetry install

- This pipeline is designed to install the dependencies of a Python project that uses Poetry.
It will install the dependencies and cache them for future runs.
- The pipeline is designed to be as generic as possible, so they can be easily reused in any project.
- This repository is a part of the generic GitHub Actions pipeline collection that can be used in any project.

## Usage

Here is a basic example on how you can integrate it in your project.

<details>
  <summary>Example workflow</summary>

This workflow is executed automatically on push to the main branch, on a pull request and can also be executed manually from the actions tab `workflow_dispatch`.

In the code below you need to replace `<python_version>` with the Python version you want to use. For example `3.11` or `3.9`.

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
        uses: actions/checkout@v4

      # Using the action
      - name: Install dependencies
        uses: minvws/action-python-poetry-install/.github/actions/poetry-install@main
        with:
          python_version: <python_version>
```

</details>

### Configuration

The action has inputs. The inputs are:

- python_version: Semver version of the Python version you want to use. For example `3.11` or `3.9`.

## Contributing

If you want to contribute a new pipeline, please check the reusable workflow guidelines in the
[GitHub documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows#creating-a-reusable-workflow).
