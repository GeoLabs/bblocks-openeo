This Building Block proposes a schema representation of the OpenEO process [`lte`](https://processes.openeo.org/#lte) — *Less than or equal to comparison*. It models the `arguments` object of a process graph node invoking `lte`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is less than or equal to `y`.

**Remarks:**

* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* If the operands are not equal (see process `eq()`) and any of them is not the data type `number`, the process returns `false`.
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`lte`](https://processes.openeo.org/#lte) ([openeo-processes/lte.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/lte.json)).
