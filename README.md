# has-value [![NPM version](https://badge.fury.io/js/has-value.svg)](http://badge.fury.io/js/has-value)  [![Build Status](https://travis-ci.org/jonschlinkert/has-value.svg)](https://travis-ci.org/jonschlinkert/has-value)

> Returns true if a value exists, false if empty. Works with deeply nested values using object paths.

- [Install](#install)
- [Related projects](#related-projects)
- [Usage](#usage)
- [isEmpty](#isempty)
- [Contributing](#contributing)
- [Running tests](#running-tests)
- [Author](#author)
- [License](#license)

**Works for:**

* booleans
* functions
* numbers (pass `true` as the last arg to treat zero as a value instead of falsey)
* strings
* nulls
* object
* arrays

## Install

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i has-value --save
```

## Related projects

* [get-object](https://www.npmjs.com/package/get-object): Get a property from an object using dot (object path) notation. | [homepage](https://github.com/jonschlinkert/get-object)
* [get-property](https://www.npmjs.com/package/get-property): Get a nested property or its value from an object using simple `  a.b.c` paths. | [homepage](https://github.com/jonschlinkert/get-property)
* [get-value](https://www.npmjs.com/package/get-value): Use property paths (`  a.b.c`) to get a nested value from an object. | [homepage](https://github.com/jonschlinkert/get-value)
* [set-value](https://www.npmjs.com/package/set-value): Create nested values and any intermediaries using dot notation (`'a.b.c'`) paths. | [homepage](https://github.com/jonschlinkert/set-value)

## Usage

Works with nested object paths or a single value:

```js
var hasValue = require('has-value');

hasValue({a: {b: {c: 'foo'}}} 'a.b.c');
//=> true

hasValue('a');
//=> true

hasValue('');
//=> false

hasValue(1);
//=> true

hasValue(0);
//=> false

hasValue(0, true); // pass `true` as the last arg to treat zero as a value
//=> true

hasValue({a: 'a'}});
//=> true

hasValue({}});
//=> false

hasValue(['a']);
//=> true

hasValue([]);
//=> false

hasValue(function(foo) {}); // function length/arity
//=> true

hasValue(function() {});
//=> false

hasValue(true);
hasValue(false);
//=> true
```

## isEmpty

To do the opposite and test for empty values, do:

```js
function isEmpty(o, isZero) {
  return !hasValue.apply(hasValue, arguments);
}
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/has-value/issues/new).

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2014-2015 Jon Schlinkert
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on November 23, 2015._