# Onlishop CLI GitHub Action

Easily install the [Onlishop CLI](https://github.com/onlishop/onlishop-cli) in your GitHub Actions workflows. Ready-to-use for building and packaging Onlishop extensions in your CI pipelines.

## Prerequisites

- A GitHub repository using GitHub Actions.
- Recommended: Use on a Linux runner (e.g., `ubuntu-latest`).

## Setup

Create a file in your repository (e.g., `.github/workflows/onlishop-cli.yml`) with the following contents:

```yaml
name: onlishop-cli

on:
  pull_request:
  push:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Install Onlishop CLI
        uses: onlishop/onlishop-cli-action@v1

      - name: Build and Package Extension
        run: onlishop-cli extension zip .
```

## More Information

For more Onlishop CLI documentation, visit [our developer docs](https://developer.onlishop.com/docs/products/cli/).
