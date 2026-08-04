This Building Block proposes a schema representation of the OpenEO process [`subtract`](https://processes.openeo.org/#subtract) — *Subtraction of two numbers*. It models the `arguments` object of a process graph node invoking `subtract`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Subtracts argument `y` from the argument `x` (*`x - y`*) and returns the computed result.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

## Source

OpenEO Processes specification: [`subtract`](https://processes.openeo.org/#subtract) ([openeo-processes/subtract.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/subtract.json)).
