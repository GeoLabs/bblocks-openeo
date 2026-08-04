This Building Block proposes a schema representation of the OpenEO process [`divide`](https://processes.openeo.org/#divide) — *Division of two numbers*. It models the `arguments` object of a process graph node invoking `divide`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Divides argument `x` by the argument `y` (*`x / y`*) and returns the computed result.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. A division by zero results in:

- +infinity for `x` > 0,
- -infinity for `x` < 0,
- `NaN` for `x` = 0,
- or otherwise, throws a `DivisionByZero` exception if the other options are not supported by the processing environment.

## Exceptions

- `DivisionByZero`: Division by zero is not supported.

## Source

OpenEO Processes specification: [`divide`](https://processes.openeo.org/#divide) ([openeo-processes/divide.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/divide.json)).
