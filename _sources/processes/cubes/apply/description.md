This Building Block proposes a schema representation of the OpenEO process [`apply`](https://processes.openeo.org/#apply) — *Apply a process to each value*. It models the `arguments` object of a process graph node invoking `apply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to each value in the data cube (i.e. a local operation). In contrast, the process `apply_dimension()` applies a process to all values along a particular dimension.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `x`: The value to process.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Source

OpenEO Processes specification: [`apply`](https://processes.openeo.org/#apply) ([openeo-processes/apply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply.json)).
