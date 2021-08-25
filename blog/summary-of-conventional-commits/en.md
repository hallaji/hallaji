---
title: 'Summary of Conventional Commits'
date: '2021-08-25'
tags:
  - git
  - commit
  - message
seo:
  title: 'Summary of Conventional Commits'
  description: A lightweight convention on top of Git commit messages
  openGraph:
    images:
      - url: 'https://hallaji.com/blog/summary-of-conventional-commits/git.png'
        width: 1606
        height: 726
        alt: Summary of Conventional Commits
---

[conventional-commits]: https://www.conventionalcommits.org/
[git]: /blog/summary-of-conventional-commits/git.svg

Conventional commits is a lightweight convention on top of commit messages. The specification doesn’t change the native git commit message guidelines but rather adds a structure to it. It provides an easy set of rules for creating an explicit commit history. This convention fits perfectly with semantic versioning, by describing the features, fixes, and breaking changes made in commit messages.

---

![Screenshot][git]

## Structure of commit message

```text
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Commit types

| Type | | SemVer |
| --- | --- | --- |
| any of following types | - A commit that has a footer:<br />`BREAKING CHANGE: <description>`<br /><br />AND/OR<br /><br /> - A commit that has a ! after the type or optional scope:<br />`<type>[optional scope]!: <description>`  |    `MAJOR`<br />Breaking Change |
| `feat` | A new feature, introducing a new feature to the codebase | `MINOR` |
| `fix`  | A bug fix, patching a bug in your codebase | `PATCH` |
| `refactor` | A change that neither fixes a bug nor adds a feature | - |
| `docs` | Documentation only changes | - |
| `style` | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc) | - |
| `perf` | A code change that improves performance | - |
| `test` | Adding missing or correcting existing tests | - |
| `chore` | Changes to the build process or auxiliary tools and libraries such as documentation generation | - |
| `ci` | Changes to the continuous integration | - |
| `build` | Changes to the build process or code generation | - |

## Commit scope

A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parentheses.

## Commit description (summary portion only)

- Use imperative tone. e.g. `add` instead of `added`
- Start with a lowercase and don’t end with a dot

## Template file

Create a template file in your home directory `~/.gitmessage` for a neat summary every time you run git commit command.

```text

# ███╗   ███╗███████╗███████╗███████╗ █████╗  ██████╗ ███████╗
# ████╗ ████║██╔════╝██╔════╝██╔════╝██╔══██╗██╔════╝ ██╔════╝
# ██╔████╔██║█████╗  ███████╗███████╗███████║██║  ███╗█████╗
# ██║╚██╔╝██║██╔══╝  ╚════██║╚════██║██╔══██║██║   ██║██╔══╝
# ██║ ╚═╝ ██║███████╗███████║███████║██║  ██║╚██████╔╝███████╗
# ╚═╝     ╚═╝╚══════╝╚══════╝╚══════╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝
# <type>[optional scope]: <description>
#
# [optional body]
#
# [optional footer(s)]
# +-----------+----------------------------------------------------------+----------+
# | Type      |                                                          | SemVer   |
# +-----------+----------------------------------------------------------+----------+
# | any of    | A commit that has a footer:                              | MAJOR    |
# | following | BREAKING CHANGE: <description>                           |          |
# | types     |                                                          | BREAKING |
# |           | AND/OR                                                   | CHANGE   |
# |           |                                                          |          |
# |           | A commit that has a ! after the type or optional scope:  |          |
# |           | <type>[optional scope]!: <description>                   |          |
# +-----------+----------------------------------------------------------+----------+
# | feat      | A new feature, introducing a new feature to the codebase | MINOR    |
# +-----------+----------------------------------------------------------+----------+
# | fix       | A bug fix, patching a bug in your codebase               | PATCH    |
# +-----------+----------------------------------------------------------+----------+
# | refactor  | A change that neither fixes a bug nor adds a feature     | -        |
# +-----------+----------------------------------------------------------+----------+
# | docs      | Documentation only changes                               | -        |
# +-----------+----------------------------------------------------------+----------+
# | style     | Changes that do not affect the meaning of the code       | -        |
# |           | (white-space, formatting, missing semi-colons, etc)      |          |
# +-----------+----------------------------------------------------------+----------+
# | perf      | A code change that improves performance                  | -        |
# +-----------+----------------------------------------------------------+----------+
# | test      | Adding missing or correcting existing tests              | -        |
# +-----------+----------------------------------------------------------+----------+
# | chore     | Changes to the build process or auxiliary tools and      | -        |
# |           | libraries such as documentation generation               |          |
# +-----------+----------------------------------------------------------+----------+
# | ci        | Changes to the continuous integration                    | -        |
# +-----------+----------------------------------------------------------+----------+
# | build     | Changes to the build process or code generation          | -        |
# +-----------+----------------------------------------------------------+----------+
#
# Note: A scope may be provided to a commit’s type, to provide additional contextual
# information and is contained within parentheses.
```

## Examples

### Different types of commits

```text
feat(api): add an endpoint for user profile updates
```

```text
fix(profile): bug in user email update
```

```text
refactor: extract repeated logic out of user profile controller
```

```text
chore: add editor configurations
```

### Breaking change

```text
refactor!: drop support for node 0.12
```

```text
feat: drop support for node 0.12

BREAKING CHANGE: node version 0.12 is no longer supported.
```

```text
fix(api)!: drop support for node 0.12

Neither of these versions are supported by the Node project anymore
and continuing support for them was already preventing us from
picking up important fixes in other dependencies.

BREAKING CHANGE: node version 0.12 is no longer supported.
```

## Why?

- Automatically generating change logs.
- Automatically determining a semantic version bump (based on the types of commits landed).
- Communicating the nature of changes to teammates, the public, and other stakeholders.
- Triggering build and publish processes.
- Making it easier for people to contribute to your projects, by allowing them to explore a more structured commit history.
- Making it easier to write automated tools

Read more on [Conventional Commits specification][conventional-commits]
