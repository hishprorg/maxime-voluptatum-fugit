# @hishprorg/maxime-voluptatum-fugit <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Define a data property on an object. Will fall back to assignment in an engine without descriptors.

The three `non*` argument can also be passed `null`, which will use the existing state if available.

The `loose` argument will mean that if you attempt to set a non-normal data property, in an environment without descriptor support, it will fall back to normal assignment.

## Usage

```javascript
var defineDataProperty = require('@hishprorg/maxime-voluptatum-fugit');
var assert = require('assert');

var obj = {};
defineDataProperty(obj, 'key', 'value');
defineDataProperty(
	obj,
	'key2',
	'value',
	true, // nonEnumerable, optional
	false, // nonWritable, optional
	true, // nonConfigurable, optional
	false // loose, optional
);

assert.deepEqual(
	Object.getOwnPropertyDescriptors(obj),
	{
		key: {
			configurable: true,
			enumerable: true,
			value: 'value',
			writable: true,
		},
		key2: {
			configurable: false,
			enumerable: false,
			value: 'value',
			writable: true,
		},
	}
);
```

[package-url]: https://npmjs.org/package/@hishprorg/maxime-voluptatum-fugit
[npm-version-svg]: https://versionbadg.es/ljharb/@hishprorg/maxime-voluptatum-fugit.svg
[deps-svg]: https://david-dm.org/ljharb/@hishprorg/maxime-voluptatum-fugit.svg
[deps-url]: https://david-dm.org/ljharb/@hishprorg/maxime-voluptatum-fugit
[dev-deps-svg]: https://david-dm.org/ljharb/@hishprorg/maxime-voluptatum-fugit/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@hishprorg/maxime-voluptatum-fugit#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@hishprorg/maxime-voluptatum-fugit.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@hishprorg/maxime-voluptatum-fugit.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@hishprorg/maxime-voluptatum-fugit.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@hishprorg/maxime-voluptatum-fugit
[codecov-image]: https://codecov.io/gh/ljharb/@hishprorg/maxime-voluptatum-fugit/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@hishprorg/maxime-voluptatum-fugit/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@hishprorg/maxime-voluptatum-fugit
[actions-url]: https://github.com/hishprorg/maxime-voluptatum-fugit/actions
