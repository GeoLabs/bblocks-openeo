
# Count (Schema)

`ogc.openeo.processes.arrays.count` *v0.1*

Count the number of elements

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`count`](https://processes.openeo.org/#count) — *Count the number of elements*. It models the `arguments` object of a process graph node invoking `count`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the number of elements in an array that matches the specified condition.

**Remarks:**

* Counts the number of valid elements by default (`condition` is set to `null`). A valid element is every element for which `is_valid()` returns `true`.
* To count all elements in a list set the `condition` parameter to boolean `true`.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `x`: The value of the current element being processed.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the element should increase the counter, otherwise `false`.

## Source

OpenEO Processes specification: [`count`](https://processes.openeo.org/#count) ([openeo-processes/count.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/count.json)).

## Examples

### Example 1
Calling `count` with these arguments returns `0`.
#### json
```json
{
  "data": []
}
```


### Example 2
Calling `count` with these arguments returns `4`.
#### json
```json
{
  "data": [
    1,
    0,
    3,
    2
  ]
}
```


### Example 3
Calling `count` with these arguments returns `1`.
#### json
```json
{
  "data": [
    "ABC",
    null
  ]
}
```


### Example 4
Calling `count` with these arguments returns `2`.
#### json
```json
{
  "data": [
    false,
    null
  ],
  "condition": true
}
```


### Example 5
Calling `count` with these arguments returns `3`.

Note: this official OpenEO example represents `condition` as a bare process-node map, without the `process_graph` wrapper key required by the `process-graph` subtype schema. This snippet is kept verbatim for fidelity to the source and is not schema-validated; it appears to be an inconsistency in the upstream openeo-processes specification between this example and its own subtype schema.
#### text
```text
{
  "data": [
    0,
    1,
    2,
    3,
    4,
    5,
    null
  ],
  "condition": {
    "gt": {
      "process_id": "gt",
      "arguments": {
        "x": {
          "from_parameter": "element"
        },
        "y": 2
      },
      "result": true
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Count the number of elements
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  condition:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
    - title: All elements
      description: Boolean `true` counts all elements in the list.
      type: boolean
      const: true
    - title: Valid elements
      description: '`null` counts valid elements in the list.'
      type: 'null'
  context:
    description: Any data type.
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/count/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/count/schema.yaml)

## Sources

* [OpenEO Processes — count](https://processes.openeo.org/#count)
* [Open-EO/openeo-processes — count.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/count.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/count`

