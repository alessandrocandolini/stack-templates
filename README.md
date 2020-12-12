# stack-templates

Collections of project templates for the [stack](https://docs.haskellstack.org/en/stable/README/) Haskell build tool.

Templates are written in hsfiles format, using [mustache](https://mustache.github.io/). 

To create a new project based on one of these templates run  
```bash
stack <options> new <project-name> alessandrocandolini/<name of the corresponding hsfile> 
```
assuming stack is installed in the system. Here, `<options>` is any command-line option available for stack, `<project-name>` is the name of the project that will be created and `<name of the corresponding hsfile> ` is the name of a `hsfile` in this repo. For example, 
```
stack new haskell-hello-world alessandrocandolini/simpler-new-template
```
or 
```
stack --resolver nightly-2020-12-12 new <project name> alessandrocandolini/simpler-new-template
```

Refer to [Stack templates documentation](https://docs.haskellstack.org/en/stable/GUIDE/#templates) for more information on how to provide and use templates, and to the [official stack documentation](https://docs.haskellstack.org/en/stable/GUIDE/) for a comprehensive list of available options when running stack. 

## simpler-new-template

`simpler-new-template` is a template based on the standard [new-template](https://github.com/commercialhaskell/stack-templates/blob/master/new-template.hsfiles) (ie, at the time of writing the default template when running stack without a template name) but with few differences:
* removing things that are not relevant for projects that are not intended to be published on hackage (eg, changelog, etc), 
* adding few opinionated dependencies (eg, [hspec](https://hspec.github.io/) and [quickcheck](https://hackage.haskell.org/package/QuickCheck) in tests, and `text` and `containers` in the src and tests) and GHC extensions (eg, [OverloadedStrings](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/glasgow_exts.html#extension-OverloadedStrings))
* built-in support for github actions (it generates a github action to automatically run `stack test` on PR and push on the `main` branch of the project) 


