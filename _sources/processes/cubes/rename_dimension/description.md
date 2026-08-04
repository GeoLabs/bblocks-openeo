This Building Block proposes a schema representation of the OpenEO process [`rename_dimension`](https://processes.openeo.org/#rename_dimension) — *Rename a dimension*. It models the `arguments` object of a process graph node invoking `rename_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Renames a dimension in the data cube while preserving all other properties.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.
- `DimensionExists`: A dimension with the specified name already exists.

## Source

OpenEO Processes specification: [`rename_dimension`](https://processes.openeo.org/#rename_dimension) ([openeo-processes/rename_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_dimension.json)).
