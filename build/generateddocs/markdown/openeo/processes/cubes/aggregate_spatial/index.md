
# Aggregate spatial (Schema)

`ogc.openeo.processes.cubes.aggregate_spatial` *v0.1*

Zonal statistics for geometries

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`aggregate_spatial`](https://processes.openeo.org/#aggregate_spatial) — *Zonal statistics for geometries*. It models the `arguments` object of a process graph node invoking `aggregate_spatial`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Aggregates statistics for one or more geometries (e.g. zonal statistics for polygons) over the spatial dimensions. The given data cube can have multiple additional dimensions and for all these dimensions results will be computed individually.

An 'unbounded' aggregation over the full extent of the horizontal spatial dimensions can be computed with the process `reduce_spatial()`.

This process passes a list of values to the reducer. The list of values has an undefined order, therefore processes such as `last()` and `first()` that depend on the order of the values will lead to unpredictable results.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: An array with elements of any type.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the vector data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `geometries` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `TargetDimensionExists`: A dimension with the specified target dimension name already exists.

## Source

OpenEO Processes specification: [`aggregate_spatial`](https://processes.openeo.org/#aggregate_spatial) ([openeo-processes/aggregate_spatial.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_spatial.json)).

## Examples

### Example 1
Calling `aggregate_spatial` with these arguments returns `{}`.

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
  },
  "reducer": {
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
description: Zonal statistics for geometries
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  geometries:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.yaml
      deprecated: true
  reducer:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  target_dimension:
    type:
    - string
    - 'null'
  context:
    description: Any data type.
required:
- data
- geometries
- reducer

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/aggregate_spatial/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/aggregate_spatial/schema.yaml)

## Sources

* [OpenEO Processes — aggregate_spatial](https://processes.openeo.org/#aggregate_spatial)
* [Open-EO/openeo-processes — aggregate_spatial.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_spatial.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/aggregate_spatial`

