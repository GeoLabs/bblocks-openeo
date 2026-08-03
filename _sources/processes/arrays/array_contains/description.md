This Building Block proposes a schema representation of the OpenEO process [`array_contains`](https://processes.openeo.org/#array_contains) — *Check whether the array contains a given value*. It models the `arguments` object of a process graph node invoking `array_contains`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the array specified for `data` contains the value specified in `value`. Returns `true` if there's a match, otherwise `false`.

**Remarks:**

* To get the index or the label of the value found, use `array_find()`.
* All definitions for the process `eq()` regarding the comparison of values apply here as well. A no-data return value from `eq()` is handled as `false` (no match).
* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*.
* An integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`. Still, this process may return unexpectedly `false` when comparing floating-point numbers due to floating-point inaccuracy in machine-based computation.
* Temporal strings are treated as normal strings and MUST NOT be interpreted.

See the examples to check for no-data values.

## Source

OpenEO Processes specification: [`array_contains`](https://processes.openeo.org/#array_contains) ([openeo-processes/array_contains.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_contains.json)).
