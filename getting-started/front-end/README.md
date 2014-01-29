# Front-end Ecosystem

The front-end developers at [Imulus](http://imulus.com/) use a wide range of tools. Here you can learn which tools are typically involved in a client project.

## Node.js and npm

[Node.js](http://nodejs.org/) is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications. We use Node.js as a unified build system, bridging the back and front ends.

[npm](http://npmjs.org/) is the official package manager for Node.js. It is used to mange our Node dependencies. Dependencies are listed in the `package.json` file and installed into the `node_modules` folder.

A sample `package.json` file:

```javascript
{
  "name": "Imulus",
  "version": "0.0.0",
  "homepage": "http://imulus.com/",
  "author": "Imulus, LLC",
  "private": true,
  "devDependencies": {
    "grunt": "~0.4.2",
    "grunt-msbuild": "~0.1.9",
    "grunt-contrib-concat": "~0.3.0",
    "grunt-contrib-watch": "~0.5.3",
    "grunt-contrib-less": "~0.9.0",
    "grunt-contrib-uglify": "~0.2.7",
    "grunt-contrib-jshint": "~0.8.0"
  }
}
```

### Installation

Mac OS X:

```bash
brew install node
```

Windows:

```bash
cinst nodejs.install
```

If you'd prefer to use a package installer, refer to the Node.js [downloads page](http://nodejs.org/download/).

## Bower

[Bower](http://bower.io/) is a package manager for the web. It is used to manage our front-end assets when possible. Dependencies are listed in the `bower.json` file and are installed into the `vendor/bower` folder.

A sample `bower.json` file:

```javascript
{
  "name": "Imulus",
  "private": true,
  "dependencies": {
    "bootstrap": "~3.0.3",
    "retina.js": "~1.2.0"
  }
}
```

### Installation

```bash
npm install -g bower
```

## Grunt

[Grunt](http://gruntjs.com/) is a JavaScript task runner. It is used to automate the process of building our projects. It can be used to build our Visual Studio solutions in addition to our front-end assets.

A sample `Gruntfile.js` file:

```javascript
module.exports = function(grunt) {
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
      },
      build: {
        src: 'src/<%= pkg.name %>.js',
        dest: 'build/<%= pkg.name %>.min.js'
      }
    }
  });

  grunt.loadNpmTasks('grunt-contrib-uglify');
  grunt.registerTask('default', ['uglify']);
};
```

### Installation

```bash
npm install -g grunt-cli
```

## Less

[Less](http://less.github.io/) is a CSS pre-processor, meaning that it extends the CSS language, adding features that allow variables, mixins, functions and many other techniques that allow you to make CSS that is more maintainable, themable and extendable.

A sample `.less` file:

```less
@base: #f938ab;

.box-shadow(@style, @c) when (iscolor(@c)) {
  -webkit-box-shadow: @style @c;
     -moz-box-shadow: @style @c;
          box-shadow: @style @c;
}

.box-shadow(@style, @alpha: 50%) when (isnumber(@alpha)) {
  .box-shadow(@style, rgba(0, 0, 0, @alpha));
}

.box {
  border-color: lighten(@base, 30%);
  color: saturate(@base, 5%);

  div {
    .box-shadow(0 0 5px, 30%);
  }
}
```

### Installation

```bash
npm install -g less
```

