# Jupyter Extension Project/Repo Generator

## Problem
> _The problem that this enhancement addresses. If possible include code or anecdotes to describe this problem to readers._

Starting an enhancement to the Jupyter ecosystem is currently captured at best
through inspecting code examples in the wild. A great deal of (conflicting)
documentation exists, most of which assumes different and usually high degrees
of familiarity with key technologies.

## Proposed Enhancement
> _A brief (1-2 sentences) overview of the enhancement you are proposing. If
  possible include hypothetical code sample to describe how the solution would
  work to readers._

A generator (or family of generators) of bare-bones but feature complete
extension repositories would provide a concise way to document and make
executable current thinking around best practices related to development of
various kinds of Jupyter 4.x extension features, e.g. server, front-end,
widget, and kernel.

In transitioning to the 5.x line, which is still in flux,
the generator would remain relevant as a repository for
advocated approaches.

## Technical Details
> _A detailed explanation covering relevant algorithms, data structures, an API
  spec, and any other relevant technical information_

### Prior Work

#### Project-Generating Projects
- [Yeoman][]
- [cookiecutter][]
- [paster create][]

#### Generating Jupyter Widgets
- [cookiecutter-ipython-widget][]


### Key Enablers/Assumptions
[Yeoman][], a nodejs library, is probably(?) the most widely-used project
generator, usually targeted at node projects. However, it can basically do
any templated, file-tree based operation. It's also light-hearted and fun.

For proposal purposes, a Yeoman generator plugin, distributed via `npm`, is
advocated, but any other equivalent technology choice at this layer could be
selected at implementation time.

The tentative name would be `generator-jupyter-extension`

However it is "natively" packaged, this generator could be
provided-as-a-service through one or more of:
- a docker container
- a vagrantfile
- a conda environment
- hosted on mybinder.org


### User Experience


#### Get Ye Node
```shell
# brew install node
# apt-get install nodejs
# dnf install nodejs
# conda install -c nodejs
```


#### Start the Process
```shell
npm install -g yo generator-jupyter-extension
yo jupyter

        _-----_
       |       |    .------------------------------------.
       |--(o)--|    |  Welcome to the jupyter extension  |
      `---------´   |             generator!             |
       ( _´U`_ )    '------------------------------------'
       /___A___\    
        |  ~  |     
      __'.___.'__   
    ´   `  |° ´ Y `

    We're so glad that you are interested in helping grow open source,
    exploratory computing with the Jupyter Community. Come visit us at
    http://jupyter.org

    If you need any help, feel free to give a shout!

    Live Chat: http://gitter.im/jupyter
    Mailing List: mailto:jupyter@googlegroups.com
    Office Hours: ???

    If you have problems with the generator, visit:
    https://github.com/jupyter/generator-jupyter-extension

    Let's get going!
```

#### Natural Name
```shell
? What will you call this project when talking to humans,
  e.g. Super Notebook Extension?
```

#### Extension Point Selection
```shell
What Jupyter function would you like to extend? (pick some)
  ♦ JavaScript Notebook (nbextension)
  ♢ JavaScript Dashboard (nbextension)
  ♢ Server
  ♢ Content Manager
  ♢ Kernel (bare)
  ♢ Kernel (ipython-wrapped)
  ♢ Kernel (JavaScript-wrapped)
  ♢ Widgets (JavaScript-only)
  ♢ Widgets (ipython)
  ♢ Exporter (nbconvert)
  ♢ Provider (nbviewer)
  ♢ Formatter (nbviewer)
```

#### Server Name
```shell
? Ah, I see you are going to be writing some python. What will you call this
  project when importing it in the python server, e.g. superextension?
```


#### Browser Name
```shell
? Ah, I see you are going to be writing some javascript. What will you call
  this project when importing it in the browser, e.g.
  jupyter-js-super-notebook-extension?
```


#### Development Line
```shell
What versions of Jupyter do you want to support? (pick some)
  ♦ 4.x (stable)
  ♢ 4.x (development with git)
  ♢ 5.x (experimental)
  ♢ 3.x (legacy)
```


#### Distribution
```shell
How would you like to distribute your extension? (pick some)
  ♢ I decline
  ♦ PyPi
  ♢ conda
  ♢ npm
```


#### Frontend Code Transpilation
```shell
Ah, I see you are going to be writing some JavaScript. What dialect would you
like to write? (pick one)
  ♢ es5 and requirejs
  ♦ es2015 ne es6 (via babel)
  ♢ typescript
  ♢ coffeescript
```


#### Style Transpilation
```shell
Ah, I see you are going to be writing some CSS. What dialect would you like to
write? (pick one)
  ♢ css
  ♦ less
  ♢ stylus
  ♢ scss
```


#### Documentation
```shell
How would you like to document your extension? (pick some)
  ♢ I won't
  ♦ automatically generated HTML docs (esdoc|jsdoc|typedoc, sphinx)
  ♦ example notebooks
  ♢ literate (pycco, docco)
```


#### Automation Task Runner
```shell
How would you like to execute common development tasks? (pick one)
  ♦ python setup.py
  ♢ npm
  ♢ gulp
```


#### JavaScript Unit Testing
```shell
Ah, I see you are going to be writing some JavaScript. How would you like to
unit test it? (pick some)
  ♢ I won't
  ♦ mocha
  ♢ karma
  ♢ jasmine
```


#### Python Unit Testing
```shell
Ah, I see you are going to be writing some Python. How would you like to unit
test it? (pick one)
  ♢ I won't
  ♦ nose
  ♢ py.test
  ♢ unittest
```


#### Integration/Compliance Testing
```shell
How would you like to test against the Jupyter ecosystem? (pick some)
  ♢ I won't
  ♦ casperjs integration tests
  ♢ tox
  ♢ nosebook
```


#### Continuous Integration
```shell
Ah, I see you are going to run some tests. How would you like to continuously
integrate? (pick some)
  ♢ I won't
  ♦ travis-ci.org
  ♢ anaconda.org
  ♢ circle-ci.org
  ♢ coveralls.io
```


#### Continuous Delivery
```shell
Ah, I see you going to release software. Would you like to continuously deploy
git-tagged versions? (pick some)
  ♢ I won't
  ♦ pypi (via travis-ci.org)
  ♢ conda (via anaconda.org)
  ♢ hub.docker.com
  ♢ mybinder.org
```


#### Continuous Documentation
```shell
Ah, I see you are going to write documentation. Would you like to continuously
document? (choose some)
  ♢ I won't
  ♦ readthedocs.org
  ♢ doc.esdoc.org
  ♢ <user>.github.io
```


#### Linting
```shell
How would you like to ensure code quality?
  ♢ I won't
  ♦ eslint
  ♢ flake8
  ♢ jsonlint
  ♢ tslint
  ♢ coffeelint
```


#### Live Coding
```shell
What would you like to enable in your main live coding (per-save) task?
  (pick some)
  ♢ I won't
  ♦ incremental js/css build
  ♢ linting
  ♢ unit test
  ♢ integration testing (expensive!)
```


#### Commit Hooks
```shell
What would you like to ensure before being able to make a git commit?
  (pick some)
  ♢ I won't
  ♦ frontend build
  ♢ linting
  ♢ coverage
  ♢ documentation coverage
  ♢ unit testing
  ♢ integration testing (expensive!)
```


## Pros
> _A list of pros that this implementation has over other potential
  implementations._

- The end-user experience should improve, as more, higher-quality,
  better-documented extensions are made available through user's packaging
  channels that more consistently work with one another
- The developer experience of beginning a Jupyter extension would be far simpler
  and less pitfall-prone than the existing method of read doc, ask questions,
  read code, etc.
- The Jupyter extension documentation maintainer experience would shift focus to
  talking about features and process, and writing minimum viable examples:
  decisions can be captured more succinctly and seem less like "busy work".

## ... and Cons
> _A list of cons that this implementation has._

- Creation, much less maintenance of the feature/process graph, with specific
  resolutions for different combinations, will constitute a significant effort,
  and will need to track to almost all of the public APIs: merely creating
  examples of a few key combinations would be less involved work, but would
  require more human eyes to maintain confidently vs a testable scaffolding
  system.
- Documentation of the generator itself would constitute an additional burden
- Picking [Yeoman][] will reduce cross-language opportunity, vs. the more
  historically-used ecosystem base (Python)
- Developers would have to install nodejs


## Interested Contributors
> _A list of individuals who would be interested in contributing to this
  enhancement should it be accepted._


@bollwyvl

[Yeoman]: http://yeoman.io
[paster create]: http://pythonpaste.org/script/developer.html#id6
[cookiecutter]: https://github.com/audreyr/cookiecutter
[cookiecutter-ipython-widget]: https://github.com/bollwyvl/cookiecutter-ipython-widget
