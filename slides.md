title: Optimizing Your JS Workflow
output: index.html
theme: theme
controls: false
logo: theme/logo.png

-- title

# Optimizing Your JS Workflow

-- title

# Brought to you by

-- presenter

![Eric Kryski](http://gravatar.com/avatar/23aba778a7daae99348aeb0728cf4aec?s=200)

## Eric Kryski

* [<i class="fa fa-github"></i> ekryski](https://github.com/ekryski)
* [<i class="fa fa-twitter"></i> @ekryski](http://twitter.com/ekryski)
* [<i class="fa fa-home"></i> erickryski.com](http://erickryski.com)

-- sponsors

# Our Sponsors

![Assembly](img/sponsors/assembly_logo.png)

![Village Brewery](img/sponsors/village_brewery_logo.png)

![Startup Calgary](img/sponsors/startup_calgary_logo.png)

![PetroFeed](img/sponsors/petrofeed_logo.png)

--

# Last Month

* Intro to [NodeJS](http://nodejs.org) & [npm](http://npmjs.org)
* Package.json and commonJS modules
* NodeJS "hello world" http server
* Creating a file server and then making it stream
* Intro to [express](http://expressjs.com) & [socket.io](http://socket.io)
* Creating a real-time photo sharing app using [Feathers](http://feathersjs.com)

--

## Modules

```javascript
var APP = (function() {
  // Do stuff
  var privateVariable = 'Hello ',
    sayHi = function(name) {
      return privateVariable + name;
    };

  // Return API
  return {
    init : function() { /* ... */ },
    hi : sayHi
  }
})();

console.log(APP.sayHi('David'));
```

--

## Asynchronous Module Definition

```javascript
// say_hi.js
define(function() {
  var privateVariable = 'Hello ';
  return {
    sayHi : function(name) {
              return privateVariable + name;
          }
  }
});

// module.js
define(['./say_hi'], function(hiSayer) {
  return {
    result : hiSayer.sayHi('David'),
    sayHi : hiSayer
  }
});

// app.js
var module = require('./module', function(module) {
  module.sayHi('You'); // Hello You
  module.result; // -> Hello David
});
```

-- image

<img src="img/requirejs-logo.png" alt="RequireJS logo" style="max-width: 240px;">

--

## AMD -> CommonJS

```javascript
// say_hi.js
define(function(module, exports, require) {
  var privateVariable = 'Hello ';
  return {
    sayHi : function(name) {
              return privateVariable + name;
          }
  }
});

// module.js
define(['./say_hi'], function(hiSayer) {
  return {
    result : hiSayer.sayHi('David'),
    sayHi : hiSayer
  }
});

// app.js
var module = require('./module', function(module) {
  module.sayHi('You'); // Hello You
  module.result; // -> Hello David
});
```

-- image

<img src="img/browserify-logo.png" alt="Browserify logo" style="max-width: 400px;">

```bash
npm install -g browserify
npm install lodash
browserify main.js -o bundle.js
```

* Module loader & build system that lets you write CommonJS style modules for the browser.
* A lot of NodeJS modules (including core ones) will "Just Work"
* Has plugins called "transforms" that make it even more magical

-- image

<img src="img/bower-logo.png" alt="Bower logo" style="max-width: 240px;">

```bash
npm install -g bower
bower install jquery#1.10
```

* A client side package manager
* Uses `bower.json` and also leverages github

-- image

![component logo](img/component-logo.jpg)

```bash
npm install -g component
component install component/emitter
component build
```

* A client side package manager, module loader & build system
* Lets you write CommonJS style modules for the browser.
* Components are self contained with minimal styling (supports css)
* Uses `component.json` which leverages github

-- image

<img src="img/grunt-logo.png" alt="Grunt logo" style="max-height: 240px; max-width: 240px;">

```bash
npm install -g grunt-cli
grunt Gruntfile.js
```

* Build system with tons of plugins
* More "config-file-like"

-- image

<img src="img/gulp-logo.png" alt="Gulp logo" style="max-height: 240px; max-width: 240px;">

```bash
npm install -g gulp
gulp Gulpfile.js
```

* Build system also with tons of plugins
* More "code-like" & crazy fast
* Uses streams to pipe your files from one rule to another

-- image

<img src="img/combined.png" alt="Awesome Sauce">

<img src="img/omg.gif" alt="OMG" style="max-height: 240px; max-width: 240px; margin-top: -120px;">

--

# Next Month

* Why use a framework?
