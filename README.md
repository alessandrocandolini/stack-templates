# stack-templates

## stack-simpler-template

Simpler template for stack projects, based on the [new-template](https://github.com/commercialhaskell/stack-templates/blob/master/new-template.hsfiles) but few major differences:
* removing things that are not relevant for projects that are not intended to be published on hackage, 
* and with few opinionated dependencies and GHC extensions already imported (for testing, etc)
* built-in support for github actions 

### How to create a new project 

Assuming `stack` is installed in your system, run 
```bash
stack new <project name> alessandrocandolini/simpler-new-template
```
