This Building Block proposes a schema representation of the OpenEO process [`resample_spatial`](https://processes.openeo.org/#resample_spatial) — *Resample and warp the spatial dimensions*. It models the `arguments` object of a process graph node invoking `resample_spatial`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Resamples the spatial dimensions (x,y) of the data cube to a specified resolution and/or warps the data cube to the target projection. At least `resolution` or `projection` must be specified.

Related processes:

* Use `filter_bbox()` to set the target spatial extent.
* To spatially align two data cubes with each other (e.g. for merging), better use the process `resample_cube_spatial()`.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`resample_spatial`](https://processes.openeo.org/#resample_spatial) ([openeo-processes/resample_spatial.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_spatial.json)).
