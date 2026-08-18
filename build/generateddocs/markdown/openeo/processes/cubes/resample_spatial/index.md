
# Resample spatial (Schema)

`ogc.openeo.processes.cubes.resample_spatial` *v0.1*

Resample and warp the spatial dimensions

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### Example 1
Calling `resample_spatial` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "resolution": 10,
  "projection": 32632,
  "method": "bilinear"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Resample and warp the spatial dimensions
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  resolution:
    anyOf:
    - description: A single number used as the resolution for both x and y.
      type: number
      minimum: 0
    - description: A two-element array to specify separate resolutions for x (first
        element) and y (second element).
      type: array
      minItems: 2
      maxItems: 2
      items:
        type: number
        minimum: 0
  projection:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/epsg-code/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/wkt2-definition/schema.yaml
    - title: Don't change projection
      type: 'null'
  method:
    type: string
    enum:
    - average
    - bilinear
    - cubic
    - cubicspline
    - lanczos
    - max
    - med
    - min
    - mode
    - near
    - q1
    - q3
    - rms
    - sum
  align:
    type: string
    enum:
    - lower-left
    - upper-left
    - lower-right
    - upper-right
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/resample_spatial/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/resample_spatial/schema.yaml)

## Sources

* [OpenEO Processes — resample_spatial](https://processes.openeo.org/#resample_spatial)
* [Open-EO/openeo-processes — resample_spatial.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_spatial.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/resample_spatial`

