This Building Block proposes a schema representation of the OpenEO process [`multiply`](https://processes.openeo.org/#multiply) — *Multiplication of two numbers*. It models the `arguments` object of a process graph node invoking `multiply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Multiplies the two numbers `x` and `y` (*`x * y`*) and returns the computed product.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

## Exceptions

- `MultiplicandMissing`: Multiplication requires at least two numbers.

## Source

OpenEO Processes specification: [`multiply`](https://processes.openeo.org/#multiply) ([openeo-processes/multiply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/multiply.json)).
