
# Reduce dimension (Schema)

`ogc.openeo.processes.cubes.reduce_dimension` *v0.1*

Reduce dimensions

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`reduce_dimension`](https://processes.openeo.org/#reduce_dimension) — *Reduce dimensions*. It models the `arguments` object of a process graph node invoking `reduce_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a reducer to a data cube dimension by collapsing all the values along the specified dimension into an output value computed by the reducer.

The dimension is dropped. To avoid this, use `apply_dimension()` instead.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: A labeled array with elements of any type.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`reduce_dimension`](https://processes.openeo.org/#reduce_dimension) ([openeo-processes/reduce_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/reduce_dimension.json)).

## Examples

### Example 1
Calling `reduce_dimension` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
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
  },
  "dimension": "t"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Reduce dimensions
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  reducer:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  dimension:
    type: string
  context:
    description: Any data type.
required:
- data
- reducer
- dimension

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/reduce_dimension/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/reduce_dimension/schema.yaml)

## Sources

* [OpenEO Processes — reduce_dimension](https://processes.openeo.org/#reduce_dimension)
* [Open-EO/openeo-processes — reduce_dimension.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/reduce_dimension.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/reduce_dimension`

