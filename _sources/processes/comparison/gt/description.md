This Building Block proposes a schema representation of the OpenEO process [`gt`](https://processes.openeo.org/#gt) — *Greater than comparison*. It models the `arguments` object of a process graph node invoking `gt`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is strictly greater than `y`.

**Remarks:**

* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* If any operand is not the data type `number`, the process returns `false`.
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`gt`](https://processes.openeo.org/#gt) ([openeo-processes/gt.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/gt.json)).
