This Building Block proposes a schema representation of the OpenEO process [`log`](https://processes.openeo.org/#log) — *Logarithm to a base*. It models the `arguments` object of a process graph node invoking `log`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Logarithm to the base `base` of the number `x` is defined to be the inverse function of taking b to the power of x.

If any argument is a no-data value, the result will be the no-data value (or `null`).

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, having `x` set to `0` with any base results in -infinity if the processing environment supports it or otherwise an exception is thrown. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`log`](https://processes.openeo.org/#log) ([openeo-processes/log.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/log.json)).
