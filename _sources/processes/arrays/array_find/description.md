This Building Block proposes a schema representation of the OpenEO process [`array_find`](https://processes.openeo.org/#array_find) — *Get the index for a value in an array*. It models the `arguments` object of a process graph node invoking `array_find`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Returns the zero-based index of the first (or last) occurrence of the value specified by `value` in the array specified by `data` or the no-data value (or `null`) if there is no match. Use the parameter `reverse` to switch from the first to the last match.

**Remarks:**

* Use `array_contains()` to check if an array contains a value regardless of the position.
* Use `array_find_label()` to find the index for a label.
* All definitions for the process `eq()` regarding the comparison of values apply here as well. A no-data return value from `eq()` is handled as `false` (no match).
* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*.
* An integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`. Still, this process may return unexpectedly `false` when comparing floating-point numbers due to floating-point inaccuracy in machine-based computation.
* Temporal strings are treated as normal strings and MUST NOT be interpreted.
* If the specified value is an array, object or null, the process always returns the no-data value (or `null`). See the examples to find no-data values.

## Source

OpenEO Processes specification: [`array_find`](https://processes.openeo.org/#array_find) ([openeo-processes/array_find.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_find.json)).
