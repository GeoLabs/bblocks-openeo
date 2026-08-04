This Building Block proposes a schema representation of the OpenEO process [`filter_bbox`](https://processes.openeo.org/#filter_bbox) — *Spatial filter using a bounding box*. It models the `arguments` object of a process graph node invoking `filter_bbox`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Limits the data cube to the specified bounding box.

* For raster data cubes, the filter retains a pixel in the data cube if the point at the pixel center intersects with the bounding box (as defined in the Simple Features standard by the OGC). Alternatively, `filter_spatial()` can be used to filter by geometry.
* For vector data cubes, the filter retains the geometry in the data cube if the geometry is fully within the bounding box (as defined in the Simple Features standard by the OGC). All geometries that were empty or not contained fully within the bounding box will be removed from the data cube.

Alternatively, filter spatially with geometries using `filter_spatial()` (on a raster data cube) or `filter_vector()` (on a vector data cube).

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `data` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`filter_bbox`](https://processes.openeo.org/#filter_bbox) ([openeo-processes/filter_bbox.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_bbox.json)).
