This Building Block proposes a schema representation of the OpenEO process [`mod`](https://processes.openeo.org/#mod) — *Modulo*. It models the `arguments` object of a process graph node invoking `mod`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Remainder after a division of `x` by `y` for both integers and floating-point numbers.

The result of a modulo operation has the sign of the divisor. The handling regarding the sign of the result [differs between programming languages](https://en.wikipedia.org/wiki/Modulo_operation#In_programming_languages) and needs careful consideration to avoid unexpected results.

If any argument is a no-data value, the result will be the no-data value (or `null`). If `y` is set to 0 this results in:

- +infinity for `x` > 0,
- -infinity for `x` < 0,
- `NaN` for `x` = 0,
- or otherwise, throws a `DivisionByZero` exception if the other options are not supported by the processing environment.

## Exceptions

- `DivisionByZero`: Division by zero is not supported.

## Source

OpenEO Processes specification: [`mod`](https://processes.openeo.org/#mod) ([openeo-processes/mod.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mod.json)).
