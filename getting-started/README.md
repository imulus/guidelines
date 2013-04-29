# Getting Started

Getting up and running takes about 8-10 minutes.

## Here are the things we are going to install:
- [Ruby](http://www.ruby-lang.org/en/) - Everyone's favorite dynamic language
- [RubyGems](http://rubygems.org/) - Ruby's package manager
- [Rake](http://rake.rubyforge.org/) - Ruby's version of Make. We use it as a task runner for builds.
- [Bundler](http://gembundler.com/) - A Ruby dependency manager
- [Node.js](http://nodejs.org/) - JavaScript runtime
- [NPM](http://npmjs.org) - Node Package Manager
- [Banshee](https://github.com/imulus/banshee) - Tool for bundling/compiling/compressing JavaScript and CSS

<(Need directions for installing Git Bash)>

## Install Ruby

### Windows
1. Go to [http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/) and download the Ruby installer. We recommend 1.9.3-p0.
2. Open the downloaded installer and follow the steps.
3. Ensure Ruby was added to your PATH by running `which ruby` on your command line. If `which ruby` returns blank, [follow these steps](http://support.microsoft.com/kb/310519) to add Ruby to your path.

If you get the following error: `The error encountered was an SSL certificate authority error`, refer to [this gist](https://gist.github.com/fnichol/867550).

### OS X
<(Need directions for installing Ruby on OS X)>


## Install Node

### Windows
1. Go to [http://nodejs.org/](http://nodejs.org/) and click "Install". This will download the installer.
2. Open the downloaded installer and follow the steps.
3. Ensure Node was added to your PATH by running `which node` on your command line. If `which node` returns blank, [follow these steps](http://support.microsoft.com/kb/310519) to add Node to your path.

### OS X
1. Go to [http://nodejs.org/](http://nodejs.org/) and click "Install". This will download the installer.
2. Open the downloaded installer and follow the steps.
3. Ensure Node was added to your PATH by running `which node` on your command line.


## Install Bundler
1. On your command line, type `gem install bundler`.

## Install Banshee
1. On your command line, type `npm install banshee --global`.


# Our Tools

## Front End
- [CoffeeScript](http://coffeescript.org/) and [LESS](http://lesscss.org/) in lieu of vanilla JavaScript and CSS.
  - CoffeeScript is a modern language that compiles to JavaScript. It provides succinct, convenient and safe object-oriented syntax.
  - LESS is a modern superset of CSS that provides nesting, variables and abstractions. It compiles to normal CSS.
- [Twitter Bootstrap](http://twitter.github.com/bootstrap/) as a foundation for HTML and CSS structure.
  - Bootstrap is a powerful front-end framework for fast prototyping and responsive designs.

## Content Management
- [Umbraco](http://umbraco.com/) for content management. <( Need to expand here )>


## Builds
- We use a combination of Ruby, Node and MSBuild to build out projects.
- [Allen](http://github.com/imulus/allen) is a Gem that manages our build process. It provides a unified build API across all of our client projects.
- [Banshee](https://github.com/imulus/banshee) is a tool that compiles all of our front-end assets (CoffeeScript, JavaScript, LESS, CSS) into one .js and one .css file that get served. [Docs here](http://imulus.github.com/banshee/)



# Workflow
## Branching strategy
- The `master` branch is always deployable.
- Integration is done on the `develop` branch.
- Active development always happens on `feature/` branches off of develop.
- Hotfixes happen on `hotfix/` branches off master.
- Recommended reading: [Git Branching - Branching Workflows](http://git-scm.com/book/ch3-4.html).


## Executing a build
- On your command line, run `rake build`. This will execute a full build of the Solution and all of the front-end assets.
- For a full list of build commands, run `rake -T`.


