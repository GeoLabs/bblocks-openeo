
# Filter spatial (Schema)

`ogc.openeo.processes.cubes.filter_spatial` *v0.1*

Spatial filter raster data cubes using geometries

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### Example 1
Calling `filter_spatial` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "geometries": {
    "type": "Polygon",
    "coordinates": [
      [
        [
          16.1,
          48.1
        ],
        [
          16.6,
          48.1
        ],
        [
          16.6,
          48.6
        ],
        [
          16.1,
          48.6
        ],
        [
          16.1,
          48.1
        ]
      ]
    ]
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Spatial filter raster data cubes using geometries
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  geometries:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.yaml
      deprecated: true
required:
- data
- geometries

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_spatial/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_spatial/schema.yaml)

## Sources

* [OpenEO Processes — filter_spatial](https://processes.openeo.org/#filter_spatial)
* [Open-EO/openeo-processes — filter_spatial.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_spatial.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/filter_spatial`

