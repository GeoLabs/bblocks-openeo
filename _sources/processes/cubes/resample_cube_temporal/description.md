This Building Block proposes a schema representation of the OpenEO process [`resample_cube_temporal`](https://processes.openeo.org/#resample_cube_temporal) — *Resample temporal dimensions to match a target data cube*. It models the `arguments` object of a process graph node invoking `resample_cube_temporal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Resamples one or more given temporal dimensions from a source data cube to align with the corresponding dimensions of the given target data cube using the nearest neighbor method. Returns a new data cube with the resampled dimensions.

By default, this process simply takes the nearest neighbor independent of the value (including no-data values). Depending on the data cubes this may lead to values being assigned to two target timestamps. To only consider valid values in a specific range around the target timestamps, use the parameter `valid_within`.

The rare case of ties is resolved by choosing the earlier timestamps.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `target` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `DimensionMismatch`: The temporal dimensions for resampling don't match.
- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`resample_cube_temporal`](https://processes.openeo.org/#resample_cube_temporal) ([openeo-processes/resample_cube_temporal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_cube_temporal.json)).
