This Building Block proposes a schema representation of the OpenEO process [`add`](https://processes.openeo.org/#add) — *Addition of two numbers*. It models the `arguments` object of a process graph node invoking `add`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Sums up the two numbers `x` and `y` (*`x + y`*) and returns the computed sum.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

## Source

OpenEO Processes specification: [`add`](https://processes.openeo.org/#add) ([openeo-processes/add.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add.json)).
