# @patrtorg/molestiae-nulla-architecto <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Is this value a JS ArrayBuffer? This module works cross-realm/iframe, does not depend on `instanceof` or mutable properties, and despite ES6 Symbol.toStringTag.

## Example

```js
var assert = require('assert');
var isArrayBuffer = require('@patrtorg/molestiae-nulla-architecto');

assert(!isArrayBuffer(function () {}));
assert(!isArrayBuffer(null));
assert(!isArrayBuffer(function* () { yield 42; return Infinity; });
assert(!isArrayBuffer(Symbol('foo')));
assert(!isArrayBuffer(1n));
assert(!isArrayBuffer(Object(1n)));

assert(!isArrayBuffer(new Set()));
assert(!isArrayBuffer(new WeakSet()));
assert(!isArrayBuffer(new Map()));
assert(!isArrayBuffer(new WeakMap()));
assert(!isArrayBuffer(new WeakRef({})));
assert(!isArrayBuffer(new FinalizationRegistry(() => {})));
assert(!isArrayBuffer(new SharedArrayBuffer()));

assert(isArrayBuffer(new ArrayBuffer()));

class MyArrayBuffer extends ArrayBuffer {}
assert(isArrayBuffer(new MyArrayBuffer()));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@patrtorg/molestiae-nulla-architecto
[npm-version-svg]: https://versionbadg.es/inspect-js/@patrtorg/molestiae-nulla-architecto.svg
[deps-svg]: https://david-dm.org/inspect-js/@patrtorg/molestiae-nulla-architecto.svg
[deps-url]: https://david-dm.org/inspect-js/@patrtorg/molestiae-nulla-architecto
[dev-deps-svg]: https://david-dm.org/inspect-js/@patrtorg/molestiae-nulla-architecto/dev-status.svg
[dev-deps-url]: https://david-dm.org/inspect-js/@patrtorg/molestiae-nulla-architecto#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@patrtorg/molestiae-nulla-architecto.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@patrtorg/molestiae-nulla-architecto.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@patrtorg/molestiae-nulla-architecto.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@patrtorg/molestiae-nulla-architecto
[codecov-image]: https://codecov.io/gh/inspect-js/@patrtorg/molestiae-nulla-architecto/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/inspect-js/@patrtorg/molestiae-nulla-architecto/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/inspect-js/@patrtorg/molestiae-nulla-architecto
[actions-url]: https://github.com/patrtorg/molestiae-nulla-architecto/actions
