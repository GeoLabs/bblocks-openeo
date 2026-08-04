This Building Block proposes a schema representation of the OpenEO process [`mask_polygon`](https://processes.openeo.org/#mask_polygon) — *Apply a polygon mask*. It models the `arguments` object of a process graph node invoking `mask_polygon`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a (multi) polygon mask to a raster data cube. To apply a raster mask use `mask()`.

All pixels for which the point at the pixel center **does not** intersect with any polygon (as defined in the Simple Features standard by the OGC) are replaced. This behavior can be inverted by setting the parameter `inside` to `true`. The pixel values are replaced with the value specified for `replacement`, which defaults to the no-data value of the raster data cube. No data values in `data` will be left untouched by the masking operation.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `mask` (a `datacube`): must include a dimension matching `geometry` (geometry_type=['Polygon', 'MultiPolygon']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`mask_polygon`](https://processes.openeo.org/#mask_polygon) ([openeo-processes/mask_polygon.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mask_polygon.json)).
