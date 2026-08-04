This Building Block proposes a schema representation of the OpenEO process [`sd`](https://processes.openeo.org/#sd) — *Standard deviation*. It models the `arguments` object of a process graph node invoking `sd`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the sample standard deviation, which quantifies the amount of variation of an array of numbers. It is defined to be the square root of the corresponding variance (see `variance()`).

A low standard deviation indicates that the values tend to be close to the expected value, while a high standard deviation indicates that the values are spread out over a wider range.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`sd`](https://processes.openeo.org/#sd) ([openeo-processes/sd.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sd.json)).
