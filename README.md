# stack-templates

Collections of simple templates for the [stack](https://docs.haskellstack.org/en/stable/README/) Haskell build tool.

## stack-simpler-template

Simpler template for stack projects, based on the [new-template](https://github.com/commercialhaskell/stack-templates/blob/master/new-template.hsfiles) but few major differences:
* removing things that are not relevant for projects that are not intended to be published on hackage, 
* and with few opinionated dependencies and GHC extensions already imported (for testing, etc)
* built-in support for github actions 

### How to create a new project 

Assuming `stack` is installed in your system, run for example 
```bash
stack new <project name> alessandrocandolini/simpler-new-template
```
or append any other option you might want to add, for example a resolver:
```bash
stack --resolver nightly-2020-12-12 new <project name> alessandrocandolini/simpler-new-template
```
For a full list of options, refer to the [official stack documentation](https://docs.haskellstack.org/en/stable/GUIDE/)

