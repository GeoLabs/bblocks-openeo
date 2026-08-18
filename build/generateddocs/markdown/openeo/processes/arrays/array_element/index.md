
# Array element (Schema)

`ogc.openeo.processes.arrays.array_element` *v0.1*

Get an element from an array

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_element`](https://processes.openeo.org/#array_element) — *Get an element from an array*. It models the `arguments` object of a process graph node invoking `array_element`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the element with the specified index or label from the array.

Either the parameter `index` or `label` must be specified, otherwise the `ArrayElementParameterMissing` exception is thrown. If both parameters are set the `ArrayElementParameterConflict` exception is thrown.

## Exceptions

- `ArrayElementNotAvailable`: The array has no element with the specified index or label.
- `ArrayElementParameterMissing`: The process `array_element` requires either the `index` or `labels` parameter to be set.
- `ArrayElementParameterConflict`: The process `array_element` only allows that either the `index` or the `labels` parameter is set.
- `ArrayNotLabeled`: The array is not a labeled array, but the `label` parameter is set. Use the `index` instead.

## Source

OpenEO Processes specification: [`array_element`](https://processes.openeo.org/#array_element) ([openeo-processes/array_element.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_element.json)).

## Examples

### Example 1
Calling `array_element` with these arguments returns `7`.
#### json
```json
{
  "data": [
    9,
    8,
    7,
    6,
    5
  ],
  "index": 2
}
```


### Example 2
Calling `array_element` with these arguments returns `"A"`.
#### json
```json
{
  "data": [
    "A",
    "B",
    "C"
  ],
  "index": 0
}
```


### Example 3
Calling `array_element` with these arguments returns `null`.
#### json
```json
{
  "data": [],
  "index": 0,
  "return_nodata": true
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Get an element from an array
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  index:
    type: integer
    minimum: 0
  label:
    anyOf:
    - type: number
    - type: string
  return_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_element/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_element/schema.yaml)

## Sources

* [OpenEO Processes — array_element](https://processes.openeo.org/#array_element)
* [Open-EO/openeo-processes — array_element.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_element.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_element`

