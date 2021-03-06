# base-watch [![NPM version](https://img.shields.io/npm/v/base-watch.svg)](https://www.npmjs.com/package/base-watch) [![Build Status](https://img.shields.io/travis/node-base/base-watch.svg)](https://travis-ci.org/node-base/base-watch)

> Watch plugin for base applications.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install base-watch --save
```

**Heads up** this plugin requires the [base-tasks][] plugin to be registered first.

## Usage

```js
var watch = require('base-watch');

var Base = require('base');
var base = new Base();

base.use(watch());
```

If you're using [assemble](https://github.com/assemble/assemble) or [assemble-core](https://github.com/assemble/assemble-core) you can add the plugin like this:

**[assemble](https://github.com/assemble/assemble)**

```js
var watch = require('base-watch');

var assemble = require('assemble');
var app = assemble();

app.use(watch());
```

**[assemble-core](https://github.com/assemble/assemble-core)**

```js
var watch = require('base-watch');

var assemble = require('assemble-core');
var app = assemble();

app.use(watch());
```

## API

If no task(s) or function is specified, only the instance of `FSWatcher` is returned and can be used directly.
See [chokidar.watch](https://github.com/paulmillr/chokidar#api) for more information.

* `returns` **{Function}**: Returns the plugin function to be used in a [base][] application.

**Example**

```js
app.use(watch());
```

### [watch](index.js#L48)

Watch a file, directory, or glob pattern for changes and build a task or list of tasks when changes are made. Watch is powered by [chokidar][] so arguments can be anything supported by [chokidar.watch](https://github.com/paulmillr/chokidar#api).

**Params**

* `glob` **{String|Array}**: Filename, Directory name, or glob pattern to watch
* `options` **{Object}**: Additional options to be passed to [chokidar][]
* `tasks` **{String|Array|Function}**: Tasks that are passed to `.build` when files in the glob are changed.
* `returns` **{Object}**: Returns an instance of `FSWatcher` from [chokidar][]

**Example**

```js
var watcher = app.watch('templates/pages/*.hbs', ['site']);
```

## Related projects

* [base](https://www.npmjs.com/package/base): base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting… [more](https://www.npmjs.com/package/base) | [homepage](https://github.com/node-base/base)
* [base-generators](https://www.npmjs.com/package/base-generators): Adds project-generator support to your `base` application. | [homepage](https://github.com/node-base/base-generators)
* [base-tasks](https://www.npmjs.com/package/base-tasks): base-methods plugin that provides a very thin wrapper around [https://github.com/jonschlinkert/composer](https://github.com/jonschlinkert/composer) for adding task methods to… [more](https://www.npmjs.com/package/base-tasks) | [homepage](https://github.com/jonschlinkert/base-tasks)
* [chokidar](https://www.npmjs.com/package/chokidar): A neat wrapper around node.js fs.watch / fs.watchFile / fsevents. | [homepage](https://github.com/paulmillr/chokidar)
* [composer](https://www.npmjs.com/package/composer): API-first task runner with three methods: task, run and watch. | [homepage](https://github.com/doowb/composer)

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/doowb/base-watch/issues/new).

## Building docs

Generate readme and API documentation with [verb][]:

```sh
$ npm install verb && npm run docs
```

Or, if [verb][] is installed globally:

```sh
$ verb
```

## Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

## Author

**Brian Woodward**

* [github/doowb](https://github.com/doowb)
* [twitter/doowb](http://twitter.com/doowb)

## License

verb © 2016, [Brian Woodward](https://github.com/doowb).
Released under the [MIT license](https://github.com/node-base/base-watch/blob/master/LICENSE).

***

_This file was generated by [verb](https://github.com/verbose/verb), v0.9.0, on April 06, 2016._