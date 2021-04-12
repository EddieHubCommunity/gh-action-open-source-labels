# Community Template Repo

Template repo with docs and GitHub Actions etc, to create other projects.

![screenshot](https://user-images.githubusercontent.com/624760/113267767-9e331c00-92ce-11eb-8e47-efb02d3c7fa2.png)

## Usage

```yaml
name: Import open source standard labels

on:
  push:
    branches: [ main ]

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
        owner-name: ${{ github.repository_owner }}
        repository-name: ${{ github.event.repository.name }}
```

## Label standards

> To facilitate the community in finding ways to contribute that match their experiences and skillsets, we have developed a comprehensive system for labelling issues and PRs. This is an introduction to this standard labelling scheme.

> Labels consist of three fields, viz. name, description and color. Label names should have a consistent format to aid both filtering within the github UI as well as scanning visually through the list. The following format is the most suited to this task (where ⎵ denotes a single space):

```
<emoji>⎵<category>:⎵<name>
```

Using the label convention from https://opensource.creativecommons.org/contributing-code/repo-labels/

## How to update the labels

To add a new label, update the `labels.json` file and the GitHub Action will do the rest.

```json
[
    {
        "name": "good first issue",
        "color": "7f0799"
    },
    {
        "name": "help wanted",
        "color": "7f0799"
    }
]
```
## Link to Our Discord Channel:

[Join EddieHub!](https://discord.gg/Hb5C9KvDKq)
