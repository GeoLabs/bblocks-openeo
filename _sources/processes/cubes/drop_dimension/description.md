This Building Block proposes a schema representation of the OpenEO process [`drop_dimension`](https://processes.openeo.org/#drop_dimension) — *Remove a dimension*. It models the `arguments` object of a process graph node invoking `drop_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Drops a dimension from the data cube.

Dropping a dimension only works on dimensions with a single dimension label left, otherwise the process fails with a `DimensionLabelCountMismatch` exception. Dimension values can be reduced to a single value with a filter such as `filter_bands()` or the `reduce_dimension()` process. If a dimension with the specified name does not exist, the process fails with a `DimensionNotAvailable` exception.

## Exceptions

- `DimensionLabelCountMismatch`: The number of dimension labels exceeds one, which requires a reducer.
- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`drop_dimension`](https://processes.openeo.org/#drop_dimension) ([openeo-processes/drop_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/drop_dimension.json)).
