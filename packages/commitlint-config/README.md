# Welcome to the `@wr-projects/commitlint-config`

[![Discord](https://img.shields.io/badge/Discord-5865F2)]()
[![Maintainer](https://img.shields.io/badge/Maintainer-WRProjects-7F187F)]()
![./LICENSE](https://img.shields.io/github/license/wr-projects/utils)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](code_of_conduct.md)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/5323bd08dd3f4dbd91a9d889847ba2b3)](https://www.codacy.com/gh/wr-projects/utils/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=wr-projects/github-template&amp;utm_campaign=Badge_Grade)
![https://lift.sonatype.com/](https://lift.sonatype.com/api/badge/github.com/wr-projects/utils)
[![](https://img.shields.io/lgtm/alerts/g/wr-projects/utils.svg?logo=lgtm&logoWidth=18)]()

## Table Of Contents
- [About the project](#about-the-project)
- [Setup](#setup)
- [Examples](#examples)
- [Format](#format)
- [Rules](#rules)
  - [Problems](#problems)
    - [type-enum](#type-enum)
    - [type-case](#type-case)
    - [type-empty](#type-empty)
    - [scope-case](#scope-case)
    - [subject-case](#subject-case)
    - [subject-empty](#subject-empty)
    - [subject-full-stop](#subject-full-stop)
    - [subject-exclamation-mark](#subject-exclamation-mark)
    - [header-max-length](#header-max-length)
    - [body-leading-blank](#body-leading-blank)
    - [footer-leading-blank](#footer-leading-blank)
- [Code Of Conduct](#code-of-conduct)
- [How to contribute ?](#how-to-contribute)
- [Contributors](#contributors)
- [Project Owner](#project-owner)
- [Follow us](#follow-us)
- [License](#license)

## About the project 
Shareable [`commitlint`](https://commitlint.js.org/#/) config enforcing the [Angular commit convention](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#commit). Use with [@commitlint/cli](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/cli)

## Setup

```sh
pnpm install --save-dev @commitlint/cli @wr-projects/commitlint-config

echo "module.exports = {extends: ['@wr-projcts/commitlint-config']};" > .commitlintrc.js
```

## Examples
```sh
✨ feat(blog): add comment section
```

## Format
```sh
<emoji> <type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

## Rules

### Problems
The following rules are considered problems for and will yield a non-zero exit code when not met. Consult [docs/rules](https://commitlint.js.org/#/reference-rules) for a list of available rules.

#### type-enum

- Condition: is found in value `type`
- Rule: `always`
- Value
```js
[
  "🎉 init",
  "🔖 tag",
  "✨ feat",
  "🐛 bug",
  "💥 breaking",
  "🚑 critical",
  "🩹 fix",
  "🚧 wip",
  "📝 comment",
  "🛂 permissions",
  "🛂 roles",
  "🔒 security",
  "🔐 secrets",
  "💄 design",
  "🎨 animations",
  "🎨 transitions",
  "💎 improve",
  "🐎 perf",
  "♻️ refactor",
  "♿ accessibility",
  "💻 desktop",
  "📱 mobile",
  "📱💻 responsive",
  "🏁 windows",
  "🍎 macOS",
  "🐧 linux",
  "🧪 test",
  "➕ addingtest",
  "📦 build",
  "🚀 deploy",
  "👷 ci",
  "📜 devscripts",
  "📚 docs",
  "🌐 internationalize",
  "🌐 i18n",
  "🌐 localisation",
  "📊 metadata",
  "👕 lint",
  "🏗️ architectural",
  "⚡ generalupdate",
  "⬆️ upgrade",
  "⬇️ downgrade",
  "➕ add",
  "🔥 remove",
  "🚚 move",
  "🚚 rename",
  "➕ adddep",
  "➖removedep",
  "👥 contributor",
  "🐳 docker",
  "🔧 configfile",
  "👽 api",
  "📄 licence",
  "🍱 assets",
  "✏️ gitfile",
  "📸 snapshots",
  "⚗️ experiments",
  "🔍️ seo",
  "🗃️ database",
  "🔀 merge",
  "🔄needforks",
  "⚰️ dead",
  "🗑️ bad"
]
```

```sh
echo "foo: some message" # fails
echo "🩹 fix: some message" # passes
```

#### type-case
- Condition: is in case `type` `value`
- Rule: `always`
- Value
```js
'lowercase'
```

```sh
echo "FIX: some message" # fails
echo "🩹 FIX: some message" # fails
echo "🩹 fix: some message" # passes
```

#### type-empty
- Condition: is empty `type`
- Rule: `never`
```sh
echo ": some message" # fails
echo "🩹: some message" # fails
echo "🩹 fix: some message" # passes
```

#### scope-case
- Condition: is in case `scope` `value`
- Rule: `always`
```js
'lowercase'
```

```sh
echo ": some message" # fails
echo "🩹: some message" # fails
echo "🩹 fix: some message" # passes
```

#### subject-case
- Condition: is in on of the cases `subject` `['sentence-case', 'start-case', 'pascale-case', 'upper-case']`
- Rule: `never`
```sh
echo "🩹 fix(SCOPE): Some message" # fails
echo "🩹 fix(SCOPE): Some Message" # fails
echo "🩹 fix(SCOPE): SomeMessage" # fails
echo "🩹 fix(SCOPE): SOMEMESSAGE" # fails
echo "🩹 fix(scope): some message" # passes
echo "🩹 fix(scope): some Message" # passes
```

#### subject-empty
- Condition: is empty `subject`
- Rule: `never`
```sh
echo "🩹 fix:" # fails
echo "🩹 fix: some message" # passes
```

#### subject-full-stop
- Condition: ends with `subject` `value`
- Rule: `never`
- Value
```js
'.'
```

```sh
echo "🩹 fix: some message." # fails
echo "🩹 fix: some message" # passes
```

#### subject-exclamation-mark
- Condition: must not have a before the marker `subject` `!` `:`
- Rule: `never`

#### header-max-length
- Condition: has or less characters `header` `value`
- Rule: `always`
- Value
```js
72
```

```sh
echo "🩹 fix: some message that is way too long and breaks the line max-length by several characters" # fails
echo "🩹 fix: some message" # passes
```

#### body-leading-blank
- Condition: Body should have a leading blank line
- Rule: `always`
```sh
echo "🩹 fix: some message
body" # fails

echo "🩹 fix: some message

body" # passes
```

#### footer-leading-blank
- Condition: Footer should have a leading blank line
- Rule: `always`
```sh
echo "🩹 fix: some message
BREAKING CHANGE: It will be significant" # fails

echo "🩹 fix: some message

BREAKING CHANGE: It will be significant" # passes
```

## Code Of Conduct

Please read the [Code Of Conduct](https://github.com/wr-projects/utils/blob/main/.github/wiki/CODE_OF_CONDUCT.md) before interacting with the project.

## How to contribute ?

In your case, to start contributing, please fork [`@wr-projects/utils`](https://github.com/wr-projects/utils/fork) and start working on your part.
Later, feel free to contribute a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork), we will be pleased to review it with you.

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

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

