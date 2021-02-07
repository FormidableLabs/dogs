dogs 🐕
======

[![npm version][npm_img]][npm_site]
<!-- [![Actions Status][actions_img]][actions_site] -->

Formidable Dogs

## Install

```sh
$ npm install @formidable/dogs
$ yarn add @formidable/dogs
```

## Contributing

This repository is configured using [semantic-release](https://github.com/semantic-release/semantic-release) which automates the whole package release workflow including: determining the next version number, generating the release notes and publishing the package.

What does this mean for contributors? It means we need a merge commit that follows the [conventional commit format](https://www.conventionalcommits.org/en/v1.0.0/). There are lots of ways to do `semantic-release` and commit vetting, but here's how _we_ do it in this repo:

1. Our target for `semantic-release` is a "Squash and merge" GitHub pull request merge. Our repository _only_ allows this kind of merge. We aim to have the _final_ commit meet the conventional commit format.
    * **Note**: This means that along the way to that final merge commit, it doesn't matter how you commit. We don't do pre-commit hooks, nor lint individual commits in a pull request. All we check is the final merge commit to make sure it's all good.
2. This means that the thing you need to check is the **pull request title** which is what will be used in the squash and merge commit to trigger `semantic release`. We use [semantic-pull-requests](https://github.com/zeke/semantic-pull-requests) to make sure that our PRs have a title meet the eventual format needed. And no worries about changes along the way! You just need to get the PR title in appropriate shape by the time you want to merge.

There are very precise rules over how git commit messages can be formatted. This leads to **more
readable messages** that are easy to follow when looking through the **project history**. Also,
the git commit messages are used to **generate the AngularJS change log**.

### Anatomy of a pull request title

The `semantic-pull-requests` bot goes for the minimal `semantic-release` information to make doing versioning as easy as possible. For how _we_ do it in this project, you just need to focus on the PR title (that must be preserved in the squash and merge commit).

The pull request title has a special format that should include a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
```

The **scope** of the header is optional.

### What type of commits trigger a release?

Type must be one of `[build, chore, ci, docs, feat, fix, perf, refactor, revert, style, test]`.
- The types `build|ci|revert` are [undocumented](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#type) but exist in [code](https://github.com/conventional-changelog/commitlint/blob/5fd27fdcd2d88435257f888d832fc19c5bbc037f/%40commitlint/config-conventional/index.test.js#L39).

| Commit Types | Description                                         | Version Impact |
|--------------|-----------------------------------------------------|----------------|
| `chore`      | Changes to the build process                        | N/A            |
| `docs`       | Changes to documentation                            | N/A            |
| `feat`       | Changes that support a new feature                  | Patch          |
| `fix`        | Changes that fix a bug                              | Minor          |
| `perf`       | Changes that improve performance                    | Patch          |
| `refactor`   | Changes that neither fixes a bug nor adds a feature | N/A            |
| `style`      | Changes that do not affect the meaning of code      | N/A            |
| `test`       | Changes to the test process                         | N/A            |

### What about major version bumps?

Major version bumps are considered **breaking changes** for `semantic-release` and are triggered intentionally.

**Breaking changes** should start with a `!` after the commit type. This changes a usual N/A version impact of something like `refactor` or `fix` to a breaking change with `refactor!` or `fix!`.

#### Examples

Any of the following PR titles should work for the appropriate release:

* `perf: removed pictures from published package`: Patch
* `refactor(utils): change internal file utils`: N/A. Add an ad-hoc scope.
* `refactor: change internal function`: N/A
* `refactor!: remove dog .jpg files`: Major

[npm_img]: https://badge.fury.io/js/@formidable/dogs.svg
[npm_site]: http://badge.fury.io/js/@formidable/dogs
<!--
TODO(31): Add `ci.yml` actual CI.
https://github.com/FormidableLabs/dogs/issues/31
[actions_img]: https://github.com/FormidableLabs/dogs/workflows/CI/badge.svg
[actions_site]: https://github.com/FormidableLabs/dogs/actions
-->