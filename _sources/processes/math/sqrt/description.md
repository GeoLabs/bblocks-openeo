This Building Block proposes a schema representation of the OpenEO process [`sqrt`](https://processes.openeo.org/#sqrt) — *Square root*. It models the `arguments` object of a process graph node invoking `sqrt`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the square root of a real number `x`, which is equal to calculating `x` to the power of *0.5*. For negative `x`, the process returns `NaN`.

A square root of x is a number a such that *`a² = x`*. Therefore, the square root is the inverse function of a to the power of 2, but only for *a >= 0*.

No-data values are passed through.

## Source

OpenEO Processes specification: [`sqrt`](https://processes.openeo.org/#sqrt) ([openeo-processes/sqrt.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sqrt.json)).
