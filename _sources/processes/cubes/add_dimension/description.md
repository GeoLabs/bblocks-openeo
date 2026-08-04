This Building Block proposes a schema representation of the OpenEO process [`add_dimension`](https://processes.openeo.org/#add_dimension) — *Add a new dimension*. It models the `arguments` object of a process graph node invoking `add_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Adds a new named dimension to the data cube.

Afterwards, the dimension can be referred to with the specified `name`. If a dimension with the specified name exists, the process fails with a `DimensionExists` exception. The dimension label of the dimension is set to the specified `label`.

## Exceptions

- `DimensionExists`: A dimension with the specified name already exists.

## Source

OpenEO Processes specification: [`add_dimension`](https://processes.openeo.org/#add_dimension) ([openeo-processes/add_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add_dimension.json)).
