This Building Block proposes a schema representation of the OpenEO process [`arctan2`](https://processes.openeo.org/#arctan2) — *Inverse tangent of two numbers*. It models the `arguments` object of a process graph node invoking `arctan2`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc tangent of two numbers `x` and `y`. It is similar to calculating the arc tangent of *`y / x`*, except that the signs of both arguments are used to determine the quadrant of the result.

Works on radians only.
If any argument is a no-data value, the result will be the no-data value (or `null`).

## Source

OpenEO Processes specification: [`arctan2`](https://processes.openeo.org/#arctan2) ([openeo-processes/arctan2.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arctan2.json)).
