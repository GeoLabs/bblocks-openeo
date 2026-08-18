
# Filter bbox (Schema)

`ogc.openeo.processes.cubes.filter_bbox` *v0.1*

Spatial filter using a bounding box

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### Example 1
Calling `filter_bbox` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "extent": {
    "west": 16.1,
    "south": 47.2,
    "east": 16.6,
    "north": 48.6
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Spatial filter using a bounding box
type: object
properties:
  data:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  extent:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/bounding-box/schema.yaml
required:
- data
- extent

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_bbox/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_bbox/schema.yaml)

## Sources

* [OpenEO Processes — filter_bbox](https://processes.openeo.org/#filter_bbox)
* [Open-EO/openeo-processes — filter_bbox.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_bbox.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/filter_bbox`

