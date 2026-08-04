This Building Block proposes a schema representation of the OpenEO process [`trim_cube`](https://processes.openeo.org/#trim_cube) — *Remove dimension labels with no-data values*. It models the `arguments` object of a process graph node invoking `trim_cube`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Removes dimension labels solely containing no-data values. If the dimension is irregular categorical then dimension labels in the middle can be removed.

## Source

OpenEO Processes specification: [`trim_cube`](https://processes.openeo.org/#trim_cube) ([openeo-processes/trim_cube.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/trim_cube.json)).
