[![CI](https://github.com/alessandrocandolini/stack-templates/actions/workflows/ci.yml/badge.svg)](https://github.com/alessandrocandolini/stack-templates/actions/workflows/ci.yml)

# stack-templates

Collections of project templates for the [stack](https://docs.haskellstack.org/en/stable/README/) Haskell build tool.

Templates are written in hsfiles format, using [mustache](https://mustache.github.io/).

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

## cli-template

Generates a simple CLI application, with command-line arguments parsed using optparse-applicative. Tests are written in hspec, using hspec-discovery. A number of additional general-purpose common libraries are imported by default (eg, aison, neat-quasi-quote, etc)

## servant-server-template

Generates a simple servant server running on wai. The server includes only an healthcheck endpoint GET `/status` returning a pre-hardcoded 200 `{"status":"ok"}` response. The project generates also a simple test to verify the implementation of the healthcheck endpoint.


## AOC

There is a variant of `cli-template` that generates a project for Advent of Code. However this template is not as maintained as the other ones, and we don't run CI tests to save time.

## (warning) Codecov upload

Tokenless code coverage report upload to [codecov](https://app.codecov.io/) is no longer supported by [codecov-action v4](https://github.com/codecov/codecov-action). 
The templates generate a non-failing step as part of the github action CI, but if you want the coverage report uploaded you have to set the env variable `CODECOV_TOKEN` under the repo Settings > Secrets > Action > New repository secret
