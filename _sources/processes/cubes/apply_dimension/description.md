This Building Block proposes a schema representation of the OpenEO process [`apply_dimension`](https://processes.openeo.org/#apply_dimension) — *Apply a process to all values along a dimension*. It models the `arguments` object of a process graph node invoking `apply_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to all values along a dimension of a data cube. For example, if the temporal dimension is specified the process will work on the values of a time series.

The process `reduce_dimension()` also applies a process to values along a dimension, but drops the dimension afterwards. The process `apply()` applies a process to each value in the data cube.

The target dimension is the source dimension if not specified otherwise in the `target_dimension` parameter. The values in the target dimension get replaced by the computed values. The name, type and reference system are preserved.

The dimension labels are preserved when the target dimension is the source dimension and the number of values in the source dimension is equal to the number of values computed by the process. Otherwise, the dimension labels will be incrementing integers starting from zero, which can be changed using `rename_labels()` afterwards. The number of labels will be equal to the number of values computed by the process.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `data`: A labeled array with elements of any type.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`apply_dimension`](https://processes.openeo.org/#apply_dimension) ([openeo-processes/apply_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_dimension.json)).
