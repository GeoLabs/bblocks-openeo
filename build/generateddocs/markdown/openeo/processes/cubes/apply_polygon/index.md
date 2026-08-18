
# Apply polygon (Schema)

`ogc.openeo.processes.cubes.apply_polygon` *v0.1*

Apply a process to segments of the data cube

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`apply_polygon`](https://processes.openeo.org/#apply_polygon) — *Apply a process to segments of the data cube*. It models the `arguments` object of a process graph node invoking `apply_polygon`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to segments of the data cube that are defined by the given polygons. For each polygon provided, all pixels for which the point at the pixel center intersects with the polygon (as defined in the Simple Features standard by the OGC) are collected into sub data cubes. If a pixel is part of multiple of the provided polygons (e.g., when the polygons overlap), the `GeometriesOverlap` exception is thrown. Each sub data cube is passed individually to the given process.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `data`: A sub data cube of the original data cube. The sub data cubes provided cover the smallest possible grid-aligned extent of the corresponding polygon and all pixels outside of the polygon are replaced with the value given in `mask_value`.
- `context` (optional): Additional data passed by the user.

It must return: The updated sub data cube with the newly computed values and the same dimensions. The dimension properties (name, type, reference system and resolution) must remain unchanged. The labels can change, but the number of labels must remain unchanged.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `geometries` (a `datacube`): must include a dimension matching `geometry` (geometry_type=['Polygon', 'MultiPolygon']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `GeometriesOverlap`: Geometries are not allowed to overlap to avoid that pixel values are processed multiple times.

## Source

OpenEO Processes specification: [`apply_polygon`](https://processes.openeo.org/#apply_polygon) ([openeo-processes/apply_polygon.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_polygon.json)).

## Examples

### Example 1
Calling `apply_polygon` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint. `geometries` is also shown as a reference: unlike some other cube-masking processes, apply_polygon's `geometries` parameter only accepts a vector data cube (no GeoJSON literal alternative).
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "geometries": {
    "from_parameter": "geometries"
  },
  "process": {
    "process_graph": {
      "mean1": {
        "process_id": "mean",
        "arguments": {
          "data": {
            "from_parameter": "data"
          }
        },
        "result": true
      }
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Apply a process to segments of the data cube
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  geometries:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  process:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  mask_value:
    anyOf:
    - type: number
    - type: boolean
    - type: string
    - type: 'null'
  context:
    description: Any data type.
required:
- data
- geometries
- process

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply_polygon/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply_polygon/schema.yaml)

## Sources

* [OpenEO Processes — apply_polygon](https://processes.openeo.org/#apply_polygon)
* [Open-EO/openeo-processes — apply_polygon.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_polygon.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/apply_polygon`

