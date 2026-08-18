
# Mask polygon (Schema)

`ogc.openeo.processes.cubes.mask_polygon` *v0.1*

Apply a polygon mask

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`mask_polygon`](https://processes.openeo.org/#mask_polygon) — *Apply a polygon mask*. It models the `arguments` object of a process graph node invoking `mask_polygon`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a (multi) polygon mask to a raster data cube. To apply a raster mask use `mask()`.

All pixels for which the point at the pixel center **does not** intersect with any polygon (as defined in the Simple Features standard by the OGC) are replaced. This behavior can be inverted by setting the parameter `inside` to `true`. The pixel values are replaced with the value specified for `replacement`, which defaults to the no-data value of the raster data cube. No data values in `data` will be left untouched by the masking operation.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `mask` (a `datacube`): must include a dimension matching `geometry` (geometry_type=['Polygon', 'MultiPolygon']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`mask_polygon`](https://processes.openeo.org/#mask_polygon) ([openeo-processes/mask_polygon.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mask_polygon.json)).

## Examples

### Example 1
Calling `mask_polygon` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "mask": {
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
description: Apply a polygon mask
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  mask:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.yaml
      deprecated: true
  replacement:
    anyOf:
    - type: number
    - type: boolean
    - type: string
    - type: 'null'
  inside:
    type: boolean
required:
- data
- mask

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/mask_polygon/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/mask_polygon/schema.yaml)

## Sources

* [OpenEO Processes — mask_polygon](https://processes.openeo.org/#mask_polygon)
* [Open-EO/openeo-processes — mask_polygon.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mask_polygon.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/mask_polygon`

