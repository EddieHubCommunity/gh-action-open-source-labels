# Open Source issue labels generator

A GitHub action that generates the labels you want (customizable name and color) in any repository, easy and efficient.

![screenshot](https://user-images.githubusercontent.com/624760/113267767-9e331c00-92ce-11eb-8e47-efb02d3c7fa2.png)

## Usage

To use this Action, you only need the yaml file below.

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
        # force: true # optional to clear existing labels, default to true
```

## Label standards

> To facilitate the community in finding ways to contribute that match their experiences and skillsets, we have developed a comprehensive system for labelling issues and PRs. This is an introduction to this standard labelling scheme.

> Labels consist of three fields, viz. name, description and color. Label names should have a consistent format to aid both filtering within the github UI as well as scanning visually through the list. The following format is the most suited to this task (where ⎵ denotes a single space):

```
<emoji>⎵<category>:⎵<name>
```

Using the label convention from https://opensource.creativecommons.org/contributing-code/repo-labels/

## Contributing to this project

To add a new label, update the `labels.json` file and the GitHub Action will do the rest for everyone!

```json
[
    {
        "name": "good first issue",
        "color": "7f0799"
    },
    {
        "name": "💬 talk: discussion",
        "color": "f9bbe5"
    } 
]
```

> This example shows two common ways to add a label. One without emoji and the other with emoji. The preferred way is using emojis at the beginning, but there are also some labels which are commonly used without emojis.

## Socials

Join our Discord community [here](http://discord.eddiehub.org)   
Subscribe our YouTube channel [here](https://www.youtube.com/user/eddiejaoude)
