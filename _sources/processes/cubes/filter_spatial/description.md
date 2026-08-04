This Building Block proposes a schema representation of the OpenEO process [`filter_spatial`](https://processes.openeo.org/#filter_spatial) — *Spatial filter raster data cubes using geometries*. It models the `arguments` object of a process graph node invoking `filter_spatial`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Limits the raster data cube over the spatial dimensions to the specified geometries.

- For **polygons**, the filter retains a pixel in the data cube if the point at the pixel center intersects with at least one of the polygons (as defined in the Simple Features standard by the OGC).
- For **points**, the process considers the closest pixel center.
- For **lines** (line strings), the process considers all the pixels whose centers are closest to at least one point on the line.

More specifically, pixels outside of the bounding box of the given geometries will not be available after filtering. All pixels inside the bounding box that are not retained will be set to no-data values.

 Alternatively, use `filter_bbox()` to filter with a bounding box or `filter_vector()` to filter a vector data cube based on geometries. Use `mask_polygon()` to mask without changing the spatial extent of your data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `geometries` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`filter_spatial`](https://processes.openeo.org/#filter_spatial) ([openeo-processes/filter_spatial.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_spatial.json)).
