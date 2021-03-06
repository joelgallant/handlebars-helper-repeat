# handlebars-helper-repeat [![NPM version](https://img.shields.io/npm/v/handlebars-helper-repeat.svg?style=flat)](https://www.npmjs.com/package/handlebars-helper-repeat) [![NPM monthly downloads](https://img.shields.io/npm/dm/handlebars-helper-repeat.svg?style=flat)](https://npmjs.org/package/handlebars-helper-repeat) [![NPM total downloads](https://img.shields.io/npm/dt/handlebars-helper-repeat.svg?style=flat)](https://npmjs.org/package/handlebars-helper-repeat) [![Linux Build Status](https://img.shields.io/travis/helpers/handlebars-helper-repeat.svg?style=flat&label=Travis)](https://travis-ci.org/helpers/handlebars-helper-repeat)

> Handlebars block helper for repeating whatever is inside the block _n_ times.

Please consider following this project's author, [Jon Schlinkert](https://github.com/jonschlinkert), and consider starring the project to show your :heart: and support.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save handlebars-helper-repeat
```

If you find a bug or have a feature request, [please create an issue](https://github.com/helpers/handlebars-helper-repeat/issues).

## Usage

```js
const repeat = require('handlebars-helper-repeat');
handlebars.registerHelper('repeat', repeat);
```

## Register with handlebars

```js
const handlebars = require('handlebars');

// 2. register the helper, name it whatever you want
handlebars.registerHelper('repeat', require('handlebars-helper-repeat'));

// 3. register some partials
handlebars.registerPartial('button', '<button>{{text}}</button>');

// 4. use in templates
const fn = handlebars.compile('{{#repeat 2}}{{> button }}{{/repeat}}');

console.log(fn({text: 'Click me!'}));
//=> '<button>Click me!</button><button>Click me!</button>'
```

## Usage Examples

**Private variables**

A few private variables are exposed to blocks:

* `count` the total number of blocks being generated
* `index` the index of the current block
* `start` the start number to use instead of zero. Basically `index + start`

Example:

```handlebars
{{#repeat count=2 start=17}}
  {{> button }}<span>{{@index}}</span>
{{else}}
  Nothing :(
{{/repeat}}
```
Results in something like:

```html
<button>Click me!</button><span>17</span>
<button>Click me!</button><span>18</span>
```

**Index**

Output the index of the current block:

```handlebars
{{#repeat 2}}
<div id="{{@index}}"> {{> button }} </div>
{{/repeat}}
```

Results in something like:

```html
<div id="0"> <button>Click me</button> </div>
<div id="1"> <button>Click me</button> </div>
```

## About

<details>
<summary><strong>Contributing</strong></summary>

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

</details>

<details>
<summary><strong>Running Tests</strong></summary>

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

</details>

<details>
<summary><strong>Building docs</strong></summary>

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

</details>

### Related projects

You might also be interested in these projects:

* [handlebars-helpers](https://www.npmjs.com/package/handlebars-helpers): More than 130 Handlebars helpers in ~20 categories. Helpers can be used with Assemble, Generate… [more](https://github.com/helpers/handlebars-helpers) | [homepage](https://github.com/helpers/handlebars-helpers "More than 130 Handlebars helpers in ~20 categories. Helpers can be used with Assemble, Generate, Verb, Ghost, gulp-handlebars, grunt-handlebars, consolidate, or any node.js/Handlebars project.")
* [repeat-string](https://www.npmjs.com/package/repeat-string): Repeat the given string n times. Fastest implementation for repeating a string. | [homepage](https://github.com/jonschlinkert/repeat-string "Repeat the given string n times. Fastest implementation for repeating a string.")
* [template-helpers](https://www.npmjs.com/package/template-helpers): Generic JavaScript helpers that can be used with any template engine. Handlebars, Lo-Dash, Underscore, or… [more](https://github.com/jonschlinkert/template-helpers) | [homepage](https://github.com/jonschlinkert/template-helpers "Generic JavaScript helpers that can be used with any template engine. Handlebars, Lo-Dash, Underscore, or any engine that supports helper functions.")

### Author

**Jon Schlinkert**

* [LinkedIn Profile](https://linkedin.com/in/jonschlinkert)
* [GitHub Profile](https://github.com/jonschlinkert)
* [Twitter Profile](https://twitter.com/jonschlinkert)

### License

Copyright © 2018, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.6.0, on March 23, 2018._