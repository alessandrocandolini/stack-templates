# stack-templates

Collections of simple templates for the [stack](https://docs.haskellstack.org/en/stable/README/) Haskell build tool.

## stack-simpler-template

Simpler template for stack projects, based on the [new-template](https://github.com/commercialhaskell/stack-templates/blob/master/new-template.hsfiles) but with few major differences:
* removing things that are not relevant for projects that are not intended to be published on hackage (eg, changelog, etc), 
* adding few opinionated dependencies (eg, [hspec](https://hspec.github.io/) and [quickcheck](https://hackage.haskell.org/package/QuickCheck) in tests, and `text` and `containers` in the src and tests) and GHC extensions (eg, [OverloadedStrings](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/glasgow_exts.html#extension-OverloadedStrings))
* built-in support for github actions (it generates a github action to automatically run `stack test` on PR and push on the `main` branch of the project) 

### How to create a new project 

Assuming `stack` is installed in your system, to create a new project run from command-line 
```bash
stack new <project name> alessandrocandolini/simpler-new-template
```
and append any other option you might want to add, for example an explicit resolver:
```bash
stack --resolver nightly-2020-12-12 new <project name> alessandrocandolini/simpler-new-template
```
For a full list of options, refer to the [official stack documentation](https://docs.haskellstack.org/en/stable/GUIDE/)

