This Building Block proposes a schema representation of the OpenEO process [`max`](https://processes.openeo.org/#max) — *Maximum value*. It models the `arguments` object of a process graph node invoking `max`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the largest value of an array of numbers, which is equal to the first element of a sorted (i.e., ordered) version of the array.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`max`](https://processes.openeo.org/#max) ([openeo-processes/max.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/max.json)).
