# @kollorg/minus-eveniet-dolor <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Robustly `.call.bind()` a function.

## Getting started

```sh
npm install --save @kollorg/minus-eveniet-dolor
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@kollorg/minus-eveniet-dolor');
const callBound = require('@kollorg/minus-eveniet-dolor/callBound');

function f(a, b) {
	assert.equal(this, 1);
	assert.equal(a, 2);
	assert.equal(b, 3);
	assert.equal(arguments.length, 2);
}

const fBound = callBind(f);

const slice = callBound('Array.prototype.slice');

delete Function.prototype.call;
delete Function.prototype.bind;

fBound(1, 2, 3);

assert.deepEqual(slice([1, 2, 3, 4], 1, -1), [2, 3]);
```

## Tests

Clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@kollorg/minus-eveniet-dolor
[npm-version-svg]: https://versionbadg.es/ljharb/@kollorg/minus-eveniet-dolor.svg
[deps-svg]: https://david-dm.org/ljharb/@kollorg/minus-eveniet-dolor.svg
[deps-url]: https://david-dm.org/ljharb/@kollorg/minus-eveniet-dolor
[dev-deps-svg]: https://david-dm.org/ljharb/@kollorg/minus-eveniet-dolor/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@kollorg/minus-eveniet-dolor#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@kollorg/minus-eveniet-dolor.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@kollorg/minus-eveniet-dolor.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@kollorg/minus-eveniet-dolor.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@kollorg/minus-eveniet-dolor
[codecov-image]: https://codecov.io/gh/ljharb/@kollorg/minus-eveniet-dolor/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@kollorg/minus-eveniet-dolor/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@kollorg/minus-eveniet-dolor
[actions-url]: https://github.com/kollorg/minus-eveniet-dolor/actions
