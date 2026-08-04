This Building Block proposes a schema representation of the OpenEO process [`ln`](https://processes.openeo.org/#ln) — *Natural logarithm*. It models the `arguments` object of a process graph node invoking `ln`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The natural logarithm is the logarithm to the base *e* of the number `x`, which equals to using the *log* process with the base set to *e*. The natural logarithm is the inverse function of taking *e* to the power x.

No-data values are passed through.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, *`ln(0)`* results in -infinity if the processing environment supports it or otherwise an exception is thrown. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`ln`](https://processes.openeo.org/#ln) ([openeo-processes/ln.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ln.json)).
