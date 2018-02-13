## to-exponential

Converts an arbitrarily big, small, or precise number represented as a String,
to exponential notation just like JavaScript's `Number.toExponential()`.

This can be used as a unique identifier for the number's value.


### Specification

It accepts any decimal number represented as a String.

- The conversion happens without loss of precision.
- It works for high precision numbers, also for those that do not fit in a
  JavaScript 64-bit numeric variable.  
  (They still have to fit in Strings, which have some maximum length).
- It works for very large and small numbers, also with an exponent (`e...`)
  that does not fit in a 64-bit number.

Returns `false` if the String does not represent a valid decimal number.


### Examples

- For both '10.5' and '0.105E2', it returns '1.05e+1'.  
  The exponent is 'e+1' (not 'e1') for consistency with
  `Number.toExponential()`.

- For '-12324.3434716349863831487632112E-561640934731461387461933142',  
  returns: '-1.23243434716349863831487632112e-561640934731461387461933138'.
