# Community Template Repo

Template repo with docs and GitHub Actions etc, to create other projects.

## Usage

```yaml
name: Import open source standard labels

on:
  workflow_dispatch:
  schedule:
    - cron: "30 1 * * *"

jobs:
  labels:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/setup-node@v2
      with:
        node-version: '14'
    - uses: EddieHubCommunity/gh-action-open-source-labels@main
      with:
        github-token: ${{ secrets.GITHUB_TOKEN }}
```

![screenshot](https://user-images.githubusercontent.com/624760/113267767-9e331c00-92ce-11eb-8e47-efb02d3c7fa2.png)
