This Building Block proposes a schema representation of the OpenEO process [`array_apply`](https://processes.openeo.org/#array_apply) — *Apply a process to each array element*. It models the `arguments` object of a process graph node invoking `array_apply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to each individual value in the array. This is basically what other languages call either a `for each` loop or a `map` function.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `index`: The zero-based index of the current element being processed.
- `label` (optional): The label of the current element being processed. Only populated for labeled arrays.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new array.

## Source

OpenEO Processes specification: [`array_apply`](https://processes.openeo.org/#array_apply) ([openeo-processes/array_apply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_apply.json)).
