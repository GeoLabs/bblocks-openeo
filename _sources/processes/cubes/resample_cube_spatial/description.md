This Building Block proposes a schema representation of the OpenEO process [`resample_cube_spatial`](https://processes.openeo.org/#resample_cube_spatial) — *Resample the spatial dimensions to match a target data cube*. It models the `arguments` object of a process graph node invoking `resample_cube_spatial`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Resamples the spatial dimensions (x,y) from a source data cube to align with the corresponding dimensions of the given target data cube. Returns a new data cube with the resampled dimensions.

To resample a data cube to a specific resolution or projection regardless of an existing target data cube, refer to `resample_spatial()`.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `target` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`resample_cube_spatial`](https://processes.openeo.org/#resample_cube_spatial) ([openeo-processes/resample_cube_spatial.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_cube_spatial.json)).
