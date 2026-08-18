
# Apply (Schema)

`ogc.openeo.processes.cubes.apply` *v0.1*

Apply a process to each value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`apply`](https://processes.openeo.org/#apply) — *Apply a process to each value*. It models the `arguments` object of a process graph node invoking `apply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to each value in the data cube (i.e. a local operation). In contrast, the process `apply_dimension()` applies a process to all values along a particular dimension.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `x`: The value to process.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Source

OpenEO Processes specification: [`apply`](https://processes.openeo.org/#apply) ([openeo-processes/apply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply.json)).

## Examples

### Example 1
Calling `apply` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "process": {
    "process_graph": {
      "abs1": {
        "process_id": "absolute",
        "arguments": {
          "x": {
            "from_parameter": "x"
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
description: Apply a process to each value
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  process:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  context:
    description: Any data type.
required:
- data
- process

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply/schema.yaml)

## Sources

* [OpenEO Processes — apply](https://processes.openeo.org/#apply)
* [Open-EO/openeo-processes — apply.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/apply`

