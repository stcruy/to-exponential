## to-exponential

Converts any arbitrarily big, small, or precise number represented as a String,
to exponential notation. For regular numbers it works just like JavaScript's
[`Number.toExponential()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential).

The returned String can be used as a unique identifier for the number's value.


### Specification

It accepts any decimal number represented as a String.

- It converts it to exponential notation without loss of precision.
- It works for high precision numbers, also for those that do not fit in a
  64-bit JavaScript Number variable.  
  (They still have to fit in Strings, which have some maximum length).
- It works for very large and very small numbers, also for those with an
  exponent (`e...`) that does not fit in a 64-bit JS number.

The exponent always gets a sign (+ or -), consistent with the output of
`Number.toExponential()`. So e.g. 5 becomes '5e+0' (not '5e0').

Returns `false` if the String does not represent a valid decimal number.


### Install

```
npm install to-exponential
```


### Examples

```
const toExponential = require('to-exponential');

console.dir( toExponential('0.5') );  // => '5e-1'.
console.dir( toExponential('5') );    // => '5e+0'.
console.dir( toExponential('50') );   // => '5e+1'.

console.dir( toExponential('10.5') );     // Outputs '1.05e+1'.
console.dir( toExponential('0.105e2') );  // Outputs '1.05e+1' too.

console.dir( toExponential(
  '-12324.3434716349863831487632112E-561640934731461387461933142'
) );
// => '-1.23243434716349863831487632112e-561640934731461387461933138'.
```
