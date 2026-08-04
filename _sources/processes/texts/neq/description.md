This Building Block proposes a schema representation of the OpenEO process [`neq`](https://processes.openeo.org/#neq) — *Not equal to comparison*. It models the `arguments` object of a process graph node invoking `neq`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is **not** strictly equal to `y`.

**Remarks:**

* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*. Nevertheless, an integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`.
* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`neq`](https://processes.openeo.org/#neq) ([openeo-processes/neq.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/neq.json)).
