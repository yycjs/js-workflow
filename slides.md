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

## RequireJS


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

--

## Component

--

## Browserify

--

## Grunt

--

## Gulp

--

## Gulp + Browserify = Awesome

--

# Next Month

* Why use a framework?
