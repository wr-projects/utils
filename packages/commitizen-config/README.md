# 👋 Welcome to the `@wr-projects/commitizen-config`

[![Discord](https://img.shields.io/badge/Discord-5865F2)]()
[![Maintainer](https://img.shields.io/badge/Maintainer-WRProjects-7F187F)]()
![./LICENSE](https://img.shields.io/github/license/wr-projects/github-template)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](code_of_conduct.md)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/5323bd08dd3f4dbd91a9d889847ba2b3)](https://www.codacy.com/gh/wr-projects/github-template/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=wr-projects/github-template&amp;utm_campaign=Badge_Grade)
![https://lift.sonatype.com/](https://lift.sonatype.com/api/badge/github.com/wr-projects/github-template)
[![](https://img.shields.io/lgtm/alerts/g/wr-projects/github-template.svg?logo=lgtm&logoWidth=18)]()

## Table Of Contents
- [About the project](#about-the-project)
- [Setup](#setup)
  - [Globally](#globally)
  - [Locally](#locally)
- [Examples](#examples)
- [Configuration](#configuration)
- [Usage](#usage)
- [Code Of Conduct](#code-of-conduct)
- [How to contribute ?](#how-to-contribute)
- [Contributors](#contributors)
- [Project Owner](#project-owner)
- [Follow us](#follow-us)
- [License](#license)

## About the project 

Conventional commits with great visibility of emoji

This commitizen adapter adds emoji alongside conventional commit message format from Angular team.

Colorful emojis makes it easy for you to skim through commit log and find certain kinds of commit.

This commitizen adapter basically works same to [cz-conventional-changelog](https://github.com/commitizen/cz-conventional-changelog).

## Setup

### Globally
```sh
pnpm install commitizen @wr-projects/commitizen-config

# set as default adapter for your projects
echo '{ "path": "@wr-projects/commitizen-config" }' > ~/.czrc
```

### Locally
```sh
pnpm install --save-dev commitizen @wr-projects/commitizen-config
```

## Examples
```sh
? Select the type of change you are committing: (Use arrow keys)
❯ Initial Commit        🎉   Begin a project. 
  Creation of version   🔖   Begin a project.
  Features              ✨   Introduce new features.
  Bug                   🐛   Fix a bug.
  Hotfix                🚑   Critical hotfix.
```

## Configuration

In order to use, install `commitizen` and `@wr-projects/commitizen-config`. Then, just add below to your `package.json`

```json
"config": {
  "commitizen": {
    "path": "@wr-projects/commitizen-config"
  }
},
```

## Usage

```sh
$ git cz
```

## Code Of Conduct

Please read the [Code Of Conduct](https://github.com/wr-projects/utils/blob/main/.github/wiki/CODE_OF_CONDUCT.md) before interacting with the project.

## How to contribute ?

In your case, to start contributing, please fork [`@wr-projects/utils`](https://github.com/wr-projects/utils/fork) and start working on your part.
Later, feel free to contribute a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork), we will be pleased to review it with you.

## Contributors



## Project Owner

| [![Grégoire FAVREAU](https://github.com/GregoireF.png?size=100)](https://github.com/GregoireF) |
| -------------------------------------------------- |
| [Grégoire FAVREAU](https://github.com/GregoireF)                                          |

## Follow us

* Support E-mail: [Mail](support@webreadyprojects.atlassian.net)
* Discord Channel: [Discord](https://discord.com/channels/849073103984525323/)

## License
[MIT LICENSE](https://github.com/wr-projects/utils/blob/main/packages/commitizen-config/LICENSE)

Copyright (c) [WRProjects Community](https://github.com/wr-projects)
