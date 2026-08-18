
# Array apply (Schema)

`ogc.openeo.processes.arrays.array_apply` *v0.1*

Apply a process to each array element

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_apply`](https://processes.openeo.org/#array_apply) — *Apply a process to each array element*. It models the `arguments` object of a process graph node invoking `array_apply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a process to each individual value in the array. This is basically what other languages call either a `for each` loop or a `map` function.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `index`: The zero-based index of the current element being processed.
- `label` (optional): The label of the current element being processed. Only populated for labeled arrays.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new array.

## Source

OpenEO Processes specification: [`array_apply`](https://processes.openeo.org/#array_apply) ([openeo-processes/array_apply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_apply.json)).

## Examples

### Apply absolute() to each element
Applies the `absolute` process to each element of the array.

Calling `array_apply` with these arguments returns `[1, 2, 3]`.
#### json
```json
{
  "data": [
    -1,
    2,
    -3
  ],
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
description: Apply a process to each array element
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  process:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  context:
    description: Any data type.
required:
- data
- process

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_apply/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_apply/schema.yaml)

## Sources

* [OpenEO Processes — array_apply](https://processes.openeo.org/#array_apply)
* [Open-EO/openeo-processes — array_apply.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_apply.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_apply`

