# Contributing

See the [contributing docs](https://github.com/yeoman/yeoman/blob/master/contributing.md)

Additionally for this generator:

* Please submit PRs to the `canary` branch, it is the main development branch for this generator.
* When submitting an issue, please follow the [guidelines](https://github.com/yeoman/yeoman/blob/master/contributing.md#issue-submission). Especially important is to make sure Yeoman is up-to-date, and providing the command or commands that cause the issue.
* When submitting a PR, make sure that the commit messages match the [AngularJS conventions][commit-message-format] (see below).
* When submitting a bugfix, write a test that exposes the bug and fails before applying your fix. Submit the test alongside the fix.
* When submitting a new feature, add tests that cover the feature.

To run the generator:
1. Clone it and `cd` to its root
2. `npm install`
3. `npm link` (tells NPM to look to your own version)
4. `yo angular-fullstack` as normal. It should run from your cloned version rather than the one downloaded from NPM.

## Git Commit Guidelines

These rules are adopted from the AngularJS project.

### Commit Message Format
Each commit message consists of a **header**, a **body** and a **footer**.  The header has a special
format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

Any line of the commit message cannot be longer 100 characters! This allows the message to be easier
to read on github as well as in various git tools.

### Type
Must be one of the following:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing
  semi-colons, etc)
* **refactor**: A code change that neither fixes a bug or adds a feature
* **test**: Adding missing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation
  generation

### Scope
The scope could be anything specifying place of the commit change. For example `app`,
`gen`, `docs`, `gen:view`, `gen:route`, `gen:service`, etc...

### Subject
The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot (.) at the end

###Body
Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes"
The body should include the motivation for the change and contrast this with previous behavior.

###Footer
The footer should contain any information about **Breaking Changes** and is also the place to
reference GitHub issues that this commit **Closes**.

A detailed explanation can be found in this [document][commit-message-format].

[commit-message-format]: https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y

# Releasing
*(for contributors with push access)*

The `grunt release` task will do most of the work for you, see [`grunt-release`](https://github.com/geddski/grunt-release#using-grunt-release) for valid release targets.

* Run the release task `grunt release:RELEASE_TARGET`.

* Push and publish the `angular-fullstack-deps` submodule.
```bash
$ cd angular-fullstack-deps
$ git push && npm publish
$ cd ..
```

* Push and publish `generator-angular-fullstack`.
```bash
$ git push && git push --tags
$ npm publish
```
