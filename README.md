# Overview
This repository contains reusable files including:
- `GitHub Actions workflows` that can be shared across multiple repositories.
- `CMake` files for base and test subproject.
- `.gitignore` file,
- `.clang-format` file.

# Workflows
Repository contains 2 reusable workflows. One is for building and testing on given platform, second for SonarCloud analysis and coverage reporting using SonarCloud and Codecov.

## Build & test
To use building and testing reusable workflow, place following file in your repo:
```yaml
name: Build & test

on: [push, pull_request]

jobs:
  linux:
    uses: przemek83/common/.github/workflows/build-and-test-cpp.yml@main
    with:
      platform: ubuntu-latest

  windows:
    uses: przemek83/common/.github/workflows/build-and-test-cpp.yml@main
    with:
      platform: windows-latest
```
Workflow will launch building and testing of project using CMake on Linux and Windows platforms. Check my other projects like `data-explorer` or `penna-model` for usage examples.

## Analysis and coverage
To use SonarCloud static analysis and coverage on Codecov and SonarCloud, place following file in your repo:
```yaml
name: Static analysis and coverage

on: [push, pull_request]

jobs:
  analyze:
    uses: przemek83/common/.github/workflows/static-analysis-and-coverage-cpp.yml@main
    secrets: inherit
```
Make sure that appropriate secrets:
- CODECOV_TOKEN - token for Codecov coverage reporting,
- SONAR_TOKEN - token for SonarCloud
 analysis and coverage reporting.

Are present in secrets section on GitHub. Also copy `sonar-project.properties` to your project and fill project key and project name. Check my other project like data-explorer or penna-model for usage examples.

## CMake
TODO

## .gitignore
TODO

## .clang-format
TODO
