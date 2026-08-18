
# Array filter (Schema)

`ogc.openeo.processes.arrays.array_filter` *v0.1*

Filter an array based on a condition

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_filter`](https://processes.openeo.org/#array_filter) — *Filter an array based on a condition*. It models the `arguments` object of a process graph node invoking `array_filter`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the array elements based on a logical expression so that afterwards an array is returned that only contains the values, indices and/or labels conforming to the condition.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `index`: The zero-based index of the current element being processed.
- `label` (optional): The label of the current element being processed. Only populated for labeled arrays.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the value should be kept in the array, otherwise `false`.

## Source

OpenEO Processes specification: [`array_filter`](https://processes.openeo.org/#array_filter) ([openeo-processes/array_filter.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_filter.json)).

## Examples

### Keep elements greater than 1
Filters the array to the elements for which `gt(x, 1)` returns `true`.

Calling `array_filter` with these arguments returns `[2, 3]`.
#### json
```json
{
  "data": [
    0,
    1,
    2,
    3
  ],
  "condition": {
    "process_graph": {
      "gt1": {
        "process_id": "gt",
        "arguments": {
          "x": {
            "from_parameter": "x"
          },
          "y": 1
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
description: Filter an array based on a condition
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  condition:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  context:
    description: Any data type.
required:
- data
- condition

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_filter/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_filter/schema.yaml)

## Sources

* [OpenEO Processes — array_filter](https://processes.openeo.org/#array_filter)
* [Open-EO/openeo-processes — array_filter.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_filter.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_filter`

