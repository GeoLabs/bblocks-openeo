This Building Block proposes a schema representation of the OpenEO process [`dimension_labels`](https://processes.openeo.org/#dimension_labels) — *Get the dimension labels*. It models the `arguments` object of a process graph node invoking `dimension_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives all labels for a dimension in the data cube. The labels have the same order as in the data cube.

If a dimension with the specified name does not exist, the process fails with a `DimensionNotAvailable` exception.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`dimension_labels`](https://processes.openeo.org/#dimension_labels) ([openeo-processes/dimension_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/dimension_labels.json)).
