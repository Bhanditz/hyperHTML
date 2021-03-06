# hyper(HTML)

[![donate](https://img.shields.io/badge/$-donate-ff69b4.svg?maxAge=2592000&style=flat)](https://github.com/WebReflection/donate)
[![Coverage Status](https://coveralls.io/repos/github/WebReflection/hyperHTML/badge.svg?branch=master)](https://coveralls.io/github/WebReflection/hyperHTML?branch=master)
[![Build Status](https://travis-ci.org/WebReflection/hyperHTML.svg?branch=master)](https://travis-ci.org/WebReflection/hyperHTML)
[![License: ISC](https://img.shields.io/badge/License-ISC-yellow.svg)](https://opensource.org/licenses/ISC)
[![Greenkeeper badge](https://badges.greenkeeper.io/WebReflection/hyperHTML.svg)](https://greenkeeper.io/)

<img alt="hyperHTML logo" src="https://webreflection.github.io/hyperHTML/logo/hyperhtml.svg" width="116" height="81">

A **Fast & Light Virtual DOM Alternative** available for [NodeJS](https://viperhtml.js.org/viper.html) and [NativeScript](https://viperhtml.js.org/native.html) too.

- - -

### V2 Highlights

Following most important changes in version 2:

  * fully rewritten, and [consumable](https://unpkg.com/hyperhtml@latest/esm/index.js), as [ES2015 Module](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
  * [usable via CDN](https://unpkg.com/hyperhtml@latest/min.js) as bundled global `hyperHTML` variable
  * restructured in modules, utilities, helpers, and commented all over for simplified contribution
  * **removed** `.escape` and `.adopt`, either useless or unstable. `hyperHTML.adopt` will be implemented as module a part
  * **added** support for objects as `style` attribute, fully compatible with [Preact](https://github.com/developit/preact) implementation
  * **improved** performance in numerous ways
  * **custom elements** V0 and V1 are now fully, and properly, supported through `document.importNode` and/or regular `cloneNode` tested against common polyfills
  * back to 4.6K thanks to **rollup** and its ability to merge all the things together like it was already in V1

## Documentation

A proper documentation full of examples can be found in [viperhtml.js.org](https://viperhtml.js.org/).

## Basic Example
The easiest way to describe `hyperHTML` is through [an example](https://webreflection.github.io/hyperHTML/test/tick.html).
```js
// this is hyperHTML
function tick(render) {
  render`
    <div>
      <h1>Hello, world!</h1>
      <h2>It is ${new Date().toLocaleTimeString()}.</h2>
    </div>
  `;
}
setInterval(tick, 1000,
  hyperHTML(document.getElementById('root'))
);
```

## Features

  * Zero dependencies, no polyfills needed, and it fits in about **4.6KB** (minified + brotli)
  * Uses directly native DOM, no virtual DOM involved
  * Designed for [template literals](http://www.ecma-international.org/ecma-262/6.0/#sec-template-literals), a templating feature built in to JS
  * Compatible with plain DOM elements and plain JS data structures
  * Also compatible with Babel transpiled output, hence suitable for every browser you can think of

## Compatibility

IE9+ , iOS8+ , Android 4+ and every modern Mobile or Desktop Browser.
You can verify directly through the following links:

  * [100% code coverage](https://webreflection.github.io/hyperHTML/test/) for browsers natively compatible with string literals
  * [100% code coverage](https://webreflection.github.io/hyperHTML/test/ie/) for IE9+ and browsers that need transpiled code

## Questions ?

Please ask anything you'd like to know in [StackOverflow](https://stackoverflow.com) using the tag [`hyperhtml`](https://stackoverflow.com/questions/tagged/hyperhtml) so that others can benefit from answers and examples.

#### hyper or lit ?

You can read more on this [hyperHTML vs lit-html](https://gist.github.com/WebReflection/fadcc419f5ccaae92bc167d8ff5c611b) comparison.

#### installation?

```js
npm install hyperhtml
```
If your bundler does not work with the following:
```js
// ES6
import hyperHTML from 'hyperhtml';

// CJS
const hyperHTML = require('hyperhtml');
```
You can try any of these other options.
```js
import hyperHTML from 'hyperhtml/esm';
// or
import {hyper, wire, bind, Component} from 'hyperhtml/esm';
// or
import hyperHTML from 'https://unpkg.com/hyperhtml?module';


const hyperHTML = require('hyperhtml/cjs').default;
// or
const {hyper, wire, bind, Component} = require('hyperhtml/cjs');
```
