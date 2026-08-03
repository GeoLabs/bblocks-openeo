This Building Block proposes a schema representation of the OpenEO process [`array_filter`](https://processes.openeo.org/#array_filter) — *Filter an array based on a condition*. It models the `arguments` object of a process graph node invoking `array_filter`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the array elements based on a logical expression so that afterwards an array is returned that only contains the values, indices and/or labels conforming to the condition.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `index`: The zero-based index of the current element being processed.
- `label` (optional): The label of the current element being processed. Only populated for labeled arrays.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the value should be kept in the array, otherwise `false`.

## Source

OpenEO Processes specification: [`array_filter`](https://processes.openeo.org/#array_filter) ([openeo-processes/array_filter.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_filter.json)).
