<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Int32Matrix

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Create a 32-bit signed integer matrix (i.e., a two-dimensional [ndarray][@stdlib/ndarray/ctor]).

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
Int32Matrix = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-matrix-int32@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var Int32Matrix = require( 'path/to/vendor/umd/ndarray-matrix-int32/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-matrix-int32@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.Int32Matrix;
})();
</script>
```

#### Int32Matrix( \[options] )

Returns a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor].

```javascript
var getShape = require( '@stdlib/ndarray-shape' );

var arr = new Int32Matrix();
// returns <ndarray>

var len = getShape( arr );
// returns [ 0, 0 ]
```

The function accepts the following options:

-   **order**: specifies whether an [ndarray][@stdlib/ndarray/ctor] is `'row-major'` (C-style) or `'column-major'` (Fortran-style). Default: `'row-major'`.
-   **mode**: specifies how to handle indices which exceed array dimensions (see [`ndarray`][@stdlib/ndarray/ctor]). Default: `'throw'`.
-   **submode**: a mode array which specifies for each dimension how to handle subscripts which exceed array dimensions (see [`ndarray`][@stdlib/ndarray/ctor]). If provided fewer modes than dimensions, an [`ndarray`][@stdlib/ndarray/ctor]) instance recycles modes using modulo arithmetic. Default: `[ options.mode ]`.
-   **readonly**: boolean indicating whether an array should be **read-only**. Default: `false`.

#### Int32Matrix( shape\[, options] )

Returns a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor] having a specified shape.

```javascript
var getShape = require( '@stdlib/ndarray-shape' );

var arr = new Int32Matrix( [ 3, 3 ] );
// returns <ndarray>

var sh = getShape( arr );
// returns [ 3, 3 ]
```

The function accepts the following arguments:

-   **shape**: array shape. Must contain exactly two elements.
-   **options**: function options. See above.

#### Int32Matrix( M, N\[, options] )

Returns a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor] having a specified shape.

```javascript
var getShape = require( '@stdlib/ndarray-shape' );

var arr = new Int32Matrix( 3, 3 );
// returns <ndarray>

var sh = getShape( arr );
// returns [ 3, 3 ]
```

The function accepts the following arguments:

-   **M**: number of rows.
-   **N**: number of columns.
-   **options**: function options. See above.

#### Int32Matrix( obj\[, options] )

Creates a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor] from an array-like object or iterable.

```javascript
var getShape = require( '@stdlib/ndarray-shape' );

var arr = new Int32Matrix( [ [ 1, 2 ], [ 3, 4 ] ] );
// returns <ndarray>

var sh = getShape( arr );
// returns [ 2, 2 ]
```

The function accepts the following arguments:

-   **obj**: array-like object or iterable from which to generate an [ndarray][@stdlib/ndarray/ctor]. If an array-like object, the value must be a nested array (i.e., an array-like object of array-like objects), where each nested array must have the same number of elements. If an iterable, the iterable must return array-like objects, each of which must have the same number of elements.
-   **options**: function options. See above.

#### Int32Matrix( buffer\[, byteOffset\[, shape]]\[, options] )

Returns a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor] view of an [`ArrayBuffer`][@stdlib/array/buffer].

```javascript
var ArrayBuffer = require( '@stdlib/array-buffer' );
var getShape = require( '@stdlib/ndarray-shape' );

var buf = new ArrayBuffer( 64 );

var arr1 = new Int32Matrix( buf );
// returns <ndarray>

var sh1 = getShape( arr1 );
// returns [ 1, 16 ]

var arr2 = new Int32Matrix( buf, 16 );
// returns <ndarray>

var sh2 = getShape( arr2 );
// returns [ 1, 12 ]

var arr3 = new Int32Matrix( buf, 16, [ 2, 1 ] );
// returns <ndarray>

var sh3 = getShape( arr3 );
// returns [ 2, 1 ]
```

The function accepts the following arguments:

-   **buffer**: underlying [`ArrayBuffer`][@stdlib/array/buffer].
-   **byteOffset**: integer byte offset specifying the location of the first indexed element. Default: `0`.
-   **shape**: array shape. Must contain exactly two elements.
-   **options**: function options. See above.

#### Int32Matrix( buffer\[, byteOffset\[, M, N]]\[, options] )

Returns a two-dimensional 32-bit signed integer [ndarray][@stdlib/ndarray/ctor] view of an [`ArrayBuffer`][@stdlib/array/buffer].

```javascript
var ArrayBuffer = require( '@stdlib/array-buffer' );
var getShape = require( '@stdlib/ndarray-shape' );

var buf = new ArrayBuffer( 64 );

var arr = new Int32Matrix( buf, 16, 2, 1 );
// returns <ndarray>

var sh = getShape( arr );
// returns [ 2, 1 ]
```

The function accepts the following arguments:

-   **buffer**: underlying [`ArrayBuffer`][@stdlib/array/buffer].
-   **byteOffset**: integer byte offset specifying the location of the first indexed element. Default: `0`.
-   **M**: number of rows.
-   **N**: number of columns.
-   **options**: function options. See above.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   Nested arrays are flattened in lexicographic order, such that, for an input nested array `obj`, `obj[i][j]` corresponds to the element `mat.get(i, j)` in the returned two-dimensional ndarray. In other words, an input nested array is assumed to be comprised of rows. Similarly, if `obj` is an iterable, each array returned by the iterable is assumed to correspond to a matrix row.
-   If provided an `ArrayBuffer` without corresponding shape arguments, the leading dimension of the returned ndarray always has a size of one.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-array-discrete-uniform@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/blas-ext-sum@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-map@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-matrix-int32@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Create a matrix containing random values:
var x = new Int32Matrix([
    discreteUniform( 10, 0, 100 ),
    discreteUniform( 10, 0, 20 )
]);

// Compute the sum along the columns:
var v = sum( x, {
    'dims': [ -1 ]
});
console.log( ndarray2array( v ) );

// Define a function which applies a threshold to individual values:
function threshold( v ) {
    return ( v > 10 ) ? v : 0;
}

// Apply threshold:
var y = map( x, threshold );

// Recompute the sum along the columns:
v = sum( y, {
    'dims': [ -1 ]
});
console.log( ndarray2array( v ) );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/ndarray-matrix/float64`][@stdlib/ndarray/matrix/float64]</span><span class="delimiter">: </span><span class="description">create a double-precision floating-point matrix (i.e., a two-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-matrix/float32`][@stdlib/ndarray/matrix/float32]</span><span class="delimiter">: </span><span class="description">create a single-precision floating-point matrix (i.e., a two-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-matrix/complex128`][@stdlib/ndarray/matrix/complex128]</span><span class="delimiter">: </span><span class="description">create a double-precision complex floating-point matrix (i.e., a two-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-matrix/complex64`][@stdlib/ndarray/matrix/complex64]</span><span class="delimiter">: </span><span class="description">create a single-precision complex floating-point matrix (i.e., a two-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-matrix/ctor`][@stdlib/ndarray/matrix/ctor]</span><span class="delimiter">: </span><span class="description">create a matrix (i.e., a two-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-vector/int32`][@stdlib/ndarray/vector/int32]</span><span class="delimiter">: </span><span class="description">create a signed 32-bit integer vector (i.e., a one-dimensional ndarray).</span>
-   <span class="package-name">[`@stdlib/ndarray-ctor`][@stdlib/ndarray/ctor]</span><span class="delimiter">: </span><span class="description">multidimensional array constructor.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-matrix-int32.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-matrix-int32

[test-image]: https://github.com/stdlib-js/ndarray-matrix-int32/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-matrix-int32/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-matrix-int32/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-matrix-int32?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-matrix-int32.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-matrix-int32/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-matrix-int32/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-matrix-int32/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-matrix-int32/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-matrix-int32/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-matrix-int32/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-matrix-int32/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-matrix-int32/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-matrix-int32/main/LICENSE

[@stdlib/array/buffer]: https://github.com/stdlib-js/array-buffer/tree/umd

[@stdlib/ndarray/ctor]: https://github.com/stdlib-js/ndarray-ctor/tree/umd

<!-- <related-links> -->

[@stdlib/ndarray/matrix/float64]: https://github.com/stdlib-js/ndarray-matrix-float64/tree/umd

[@stdlib/ndarray/matrix/float32]: https://github.com/stdlib-js/ndarray-matrix-float32/tree/umd

[@stdlib/ndarray/matrix/complex128]: https://github.com/stdlib-js/ndarray-matrix-complex128/tree/umd

[@stdlib/ndarray/matrix/complex64]: https://github.com/stdlib-js/ndarray-matrix-complex64/tree/umd

[@stdlib/ndarray/matrix/ctor]: https://github.com/stdlib-js/ndarray-matrix-ctor/tree/umd

[@stdlib/ndarray/vector/int32]: https://github.com/stdlib-js/ndarray-vector-int32/tree/umd

<!-- </related-links> -->

</section>

<!-- /.links -->
