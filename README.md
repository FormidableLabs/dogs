# dogs
Formidable Dogs

## Contributing
This repository is configured using [semantic-release](https://github.com/semantic-release/semantic-release) which automates the whole package release workflow including: determining the next version number, generating the release notes and publishing the package.

What does this mean for contributors? Your commit messages will be linted using [commitlint](https://github.com/conventional-changelog/commitlint) and must adhere to the [conventional commit format](https://www.conventionalcommits.org/en/v1.0.0/).

There are very precise rules over how git commit messages can be formatted. This leads to **more
readable messages** that are easy to follow when looking through the **project history**. Also,
the git commit messages are used to **generate the AngularJS change log**.

### Anatomy of a commit
Each commit message consists of a **header**, a **body** and a **footer**.  The header has a special
format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer than 100 characters! This allows the message to be easier
to read on GitHub as well as in various git tools.

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
Major version bumps are considered **breaking changes** for `semantic-release` and are triggered intentionally. The footer should contain any information about major changes  breaking changes and is also the place to reference GitHub issues that this commit closes.

**Breaking changes** should start with the word `BREAKING CHANGE:` with two newlines. The rest of the commit message is then used for this.

#### Example
```
perf: removed pictures from published package

BREAKING CHANGE: The dog .jpg files have been removed from the package. 
This decreases the package size from megabytes to kilobytes.
```
