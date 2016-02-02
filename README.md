toWord
===
[![NPM version][npm-image]][npm-url] [![Build Status][build-image]][build-url] [![Coverage Status][coverage-image]][coverage-url] [![Dependencies][dependencies-image]][dependencies-url]

> Returns an unsigned 32-bit integer representing the bit sequence of a [single-precision floating-point number][ieee754].


## Installation

``` bash
$ npm install math-float32-to-word
```


## Usage

``` javascript
var toWord = require( 'math-float32-to-word' );
```

#### toWord( x )

Returns an unsigned 32-bit `integer` representing the bit sequence of a [single-precision floating-point number][ieee754].

``` javascript
var float64ToFloat32 = require( 'float64-to-float32' );

var f32 = float64ToFloat32( 1.337 );
// returns 1.3370000123977661

var w = toWord( f32 );
// returns 1068180177 => 0 01111111 01010110010001011010001
```


## Examples

``` javascript
var float64ToFloat32 = require( 'float64-to-float32' );
var toWord = require( 'math-float32-to-word' );

var word;
var f64;
var f32;
var i;

// Convert single-precision floating-point numbers to integers representing the binary literal...
for ( i = 0; i < 1000; i++ ) {
	f64 = Math.random()*100 - 50;
	f32 = float64ToFloat32( f64 );
	word = toWord( f32 );
	console.log( 'float64: %d => float32: %d => word: %d', f64, f32, word );
```

To run the example code from the top-level application directory,

``` bash
$ node ./examples/index.js
```


---
## Tests

### Unit

This repository uses [tape][tape] for unit tests. To run the tests, execute the following command in the top-level application directory:

``` bash
$ make test
```

All new feature development should have corresponding unit tests to validate correct functionality.


### Test Coverage

This repository uses [Istanbul][istanbul] as its code coverage tool. To generate a test coverage report, execute the following command in the top-level application directory:

``` bash
$ make test-cov
```

Istanbul creates a `./reports/coverage` directory. To access an HTML version of the report,

``` bash
$ make view-cov
```


### Browser Support

This repository uses [Testling][testling] for browser testing. To run the tests in a (headless) local web browser, execute the following command in the top-level application directory:

``` bash
$ make test-browsers
```

To view the tests in a local web browser,

``` bash
$ make view-browser-tests
```

<!-- [![browser support][browsers-image]][browsers-url] -->


---
## License

[MIT license](http://opensource.org/licenses/MIT).


## Copyright

Copyright &copy; 2016. The [Compute.io][compute-io] Authors.


[npm-image]: http://img.shields.io/npm/v/math-float32-to-word.svg
[npm-url]: https://npmjs.org/package/math-float32-to-word

[build-image]: http://img.shields.io/travis/math-io/float32-to-word/master.svg
[build-url]: https://travis-ci.org/math-io/float32-to-word

[coverage-image]: https://img.shields.io/codecov/c/github/math-io/float32-to-word/master.svg
[coverage-url]: https://codecov.io/github/math-io/float32-to-word?branch=master

[dependencies-image]: http://img.shields.io/david/math-io/float32-to-word.svg
[dependencies-url]: https://david-dm.org/math-io/float32-to-word

[dev-dependencies-image]: http://img.shields.io/david/dev/math-io/float32-to-word.svg
[dev-dependencies-url]: https://david-dm.org/dev/math-io/float32-to-word

[github-issues-image]: http://img.shields.io/github/issues/math-io/float32-to-word.svg
[github-issues-url]: https://github.com/math-io/float32-to-word/issues

[tape]: https://github.com/substack/tape
[istanbul]: https://github.com/gotwarlost/istanbul
[testling]: https://ci.testling.com

[compute-io]: https://github.com/compute-io
[ieee754]: https://en.wikipedia.org/wiki/IEEE_754-1985