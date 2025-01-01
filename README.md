[![CI](https://github.com/alessandrocandolini/stack-templates/actions/workflows/ci.yml/badge.svg)](https://github.com/alessandrocandolini/stack-templates/actions/workflows/ci.yml)

# stack-templates

A collection of project templates for the [Stack Haskell build tool](https://docs.haskellstack.org/en/stable/README/).

Templates are written in the hsfiles format leveraging [Mustache](https://mustache.github.io/) syntax for placeholder substitution. However, the Stack templating mechanism offers limited support for sharing common parts between templates. As a result, each template is independent, and changes to shared content must be manually updated in every template.

To create a new project based on one of these templates run
```bash
stack <options> new <project-name> alessandrocandolini/<name of the corresponding hsfile>
```
assuming stack is installed in the system. Here, `<options>` is any command-line option available for stack, `<project-name>` is the name of the project that will be created and `<name of the corresponding hsfile> ` is the name of a `hsfile` in this repo. For example,
```
stack new hello-world alessandrocandolini/cli-template
```
or
```
stack --resolver nightly-2020-12-12 new hello-world alessandrocandolini/cli-template
```

Refer to [Stack templates documentation](https://docs.haskellstack.org/en/stable/GUIDE/#templates) for more information on how to provide and use templates, and to the [official stack documentation](https://docs.haskellstack.org/en/stable/GUIDE/) for a comprehensive list of available options when running stack.

## Templates

### cli-template

Generates a simple CLI application with command-line arguments parsed using [optparse-applicative](https://hackage.haskell.org/package/optparse-applicative). Tests are written using [HSpec](https://hackage.haskell.org/package/hspec) with automatic test discovery powered by [hspec-discover](https://hspec.github.io/hspec-discover.html). By default, several general-purpose libraries are included (e.g., [aeson](https://hackage.haskell.org/package/aeson) for json parsing, [neat-interpolation](https://hackage.haskell.org/package/neat-interpolation) for multi-line support and string interpolation, etc.).

### servant-server-template

Generates a basic [Servant](https://www.servant.dev/) server running on [wai](https://hackage.haskell.org/package/wai). The server includes a single health check endpoint:
```
GET /status
```
It returns a hardcoded 200 response:
```
{"status":"ok"}
```
A simple test is also generated to verify the health check implementation. 

The template also includes libraries similar to those in the cli-template.

### AOC

A specialized variant of `cli-template` specifically designed for [Advent of Code](https://adventofcode.com/) projects.

## Codecov token

⚠️ Tokenless uploading of the code coverage reports to [Codecov](https://app.codecov.io/) is no longer supported in [codecov-action v4](https://github.com/codecov/codecov-action).

To enable the GitHub Actions CI in the generated project to automatically upload test coverage reports, make sure to set the `CODECOV_TOKEN` environment variable in the GitHub repository settings. To do this, navigate to Settings > Secrets and variables > Actions > New repository secret.
