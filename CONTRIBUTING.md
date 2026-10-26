# Welcome to the gematik contributing guide <!-- omit in toc -->

Thank you for investing your time in contributing to the PS Testdriver API!

In this guide you will get an overview how you can contribute to this project by opening an issue, creating,
reviewing and merging a pull request.

## Reporting a security vulnerability

Please check [SECURITY.md](./SECURITY.md) for information on how to report a security vulnerability.

## New contributor guide

To get an overview of the project, read the [README](./README.md). The API itself is specified in
[psTestdriver.yaml](./psTestdriver.yaml) (OpenAPI 3.0).

## Getting started

### Issues

#### Create a new issue

If you spot a problem with the API specification or the documentation, search if an issue already exists.
If a related issue doesn't exist, you can open a new issue. Feedback from primary system vendors on missing
operations or on the implementability of existing ones is especially welcome.

#### Solve an issue

Scan through our existing issues to find one that interests you. If you find an issue to work on, you are
welcome to open a PR with a fix.

### Design rules for the API

Changes to [psTestdriver.yaml](./psTestdriver.yaml) should follow the design principles described in the
[README](./README.md):

- Operations are high-level and grouped by use case, not by gematik product or specialist service.
- Long-running operations follow the asynchronous action pattern (`POST` returns `201 Created` with a `Location`
  header pointing to `/actions/{id}`).
- Versioning is done via media types (`application/gematik.psTestdriver.vX.Y.Z+json`), not via URL paths.
- Every operation is tagged as `Mandatory`, `Optional` or with the test suite that requires it.

### Coding Style

gematik projects follow the [google style guide](https://github.com/google/styleguide) conventions. Please
follow them when working on your contributions.

### Validation

- The specification must be valid OpenAPI 3.0, e.g. checked with the [Swagger Editor](https://editor.swagger.io/).
- `mvn clean compile` must succeed, as it generates code from the specification.

### Commit your update

Commit the changes once you are happy with them.

### Pull Request Process

- When you're finished with the changes, create a pull request, also known as a PR.
- To open a PR
  please [fork the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).
  When you are making changes, it is recommended that you create
  a [new branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository)
  for this purpose, based off of the main branch. After your changes are pushed back to your forked
  repository, you can then create a pull request from there.
- Don't forget to [link the PR to the issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)
  if you are solving one.
- Update the [README.md](./README.md), the documentation and the [ReleaseNotes.md](./ReleaseNotes.md) with all
  details to document the changes made by this PR.
- Increase the version numbers in [psTestdriver.yaml](./psTestdriver.yaml) (including the media types) and in
  [pom.xml](./pom.xml) to the new version that this Pull Request would represent. The versioning scheme we use
  is [SemVer](http://semver.org/).
- Once you submit your PR, a project team member will review your proposal. We may ask questions or request
  additional information.
- We may ask for changes to be made before a PR can be merged, either
  using [suggested changes](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request)
  or pull request comments. You can apply suggested changes directly through the UI. You can make any other
  changes in your fork, then commit them to your branch.
- As you update your PR and apply changes, mark each conversation
  as [resolved](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#resolving-conversations).

### Your PR is merged!

Congratulations :tada::tada: The gematik team thanks you :sparkles:.

Once your PR is merged, your contributions will be publicly visible on the [gematik github page](https://github.com/gematik/).
