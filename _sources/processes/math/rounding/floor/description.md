This Building Block proposes a schema representation of the OpenEO process [`floor`](https://processes.openeo.org/#floor) — *Round fractions down*. It models the `arguments` object of a process graph node invoking `floor`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The greatest integer less than or equal to the number `x`.

This process is *not* an alias for the `int()` process as defined by some mathematicians, see the examples for negative numbers in both processes for differences.

No-data values are passed through.

## Source

OpenEO Processes specification: [`floor`](https://processes.openeo.org/#floor) ([openeo-processes/floor.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/floor.json)).
