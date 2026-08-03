This Building Block proposes a schema representation of the OpenEO process [`count`](https://processes.openeo.org/#count) — *Count the number of elements*. It models the `arguments` object of a process graph node invoking `count`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the number of elements in an array that matches the specified condition.

**Remarks:**

* Counts the number of valid elements by default (`condition` is set to `null`). A valid element is every element for which `is_valid()` returns `true`.
* To count all elements in a list set the `condition` parameter to boolean `true`.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the element should increase the counter, otherwise `false`.

## Source

OpenEO Processes specification: [`count`](https://processes.openeo.org/#count) ([openeo-processes/count.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/count.json)).
