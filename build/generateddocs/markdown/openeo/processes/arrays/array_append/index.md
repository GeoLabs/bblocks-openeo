
# Array append (Schema)

`ogc.openeo.processes.arrays.array_append` *v0.1*

Append a value to an array

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_append`](https://processes.openeo.org/#array_append) — *Append a value to an array*. It models the `arguments` object of a process graph node invoking `array_append`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Appends a new value to the end of the array, which may also include a new label for labeled arrays.

## Exceptions

- `LabelExists`: An array element with the specified label already exists.
- `ArrayNotLabeled`: A label can't be provided as the given array is not labeled.

## Source

OpenEO Processes specification: [`array_append`](https://processes.openeo.org/#array_append) ([openeo-processes/array_append.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_append.json)).

## Examples

### Example 1
Calling `array_append` with these arguments returns `[1, 2, 3]`.
#### json
```json
{
  "data": [
    1,
    2
  ],
  "value": 3
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Append a value to an array
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  value:
    description: Any data type is allowed.
  label:
    anyOf:
    - type: number
    - type: string
    - type: 'null'
required:
- data
- value

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_append/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_append/schema.yaml)

## Sources

* [OpenEO Processes — array_append](https://processes.openeo.org/#array_append)
* [Open-EO/openeo-processes — array_append.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_append.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_append`

