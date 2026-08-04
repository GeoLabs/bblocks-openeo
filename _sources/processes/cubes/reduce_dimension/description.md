This Building Block proposes a schema representation of the OpenEO process [`reduce_dimension`](https://processes.openeo.org/#reduce_dimension) — *Reduce dimensions*. It models the `arguments` object of a process graph node invoking `reduce_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a reducer to a data cube dimension by collapsing all the values along the specified dimension into an output value computed by the reducer.

The dimension is dropped. To avoid this, use `apply_dimension()` instead.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: A labeled array with elements of any type.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`reduce_dimension`](https://processes.openeo.org/#reduce_dimension) ([openeo-processes/reduce_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/reduce_dimension.json)).
