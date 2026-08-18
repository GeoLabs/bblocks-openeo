
# Array find (Schema)

`ogc.openeo.processes.arrays.array_find` *v0.1*

Get the index for a value in an array

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_find`](https://processes.openeo.org/#array_find) — *Get the index for a value in an array*. It models the `arguments` object of a process graph node invoking `array_find`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Returns the zero-based index of the first (or last) occurrence of the value specified by `value` in the array specified by `data` or the no-data value (or `null`) if there is no match. Use the parameter `reverse` to switch from the first to the last match.

**Remarks:**

* Use `array_contains()` to check if an array contains a value regardless of the position.
* Use `array_find_label()` to find the index for a label.
* All definitions for the process `eq()` regarding the comparison of values apply here as well. A no-data return value from `eq()` is handled as `false` (no match).
* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*.
* An integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`. Still, this process may return unexpectedly `false` when comparing floating-point numbers due to floating-point inaccuracy in machine-based computation.
* Temporal strings are treated as normal strings and MUST NOT be interpreted.
* If the specified value is an array, object or null, the process always returns the no-data value (or `null`). See the examples to find no-data values.

## Source

OpenEO Processes specification: [`array_find`](https://processes.openeo.org/#array_find) ([openeo-processes/array_find.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_find.json)).

## Examples

### Example 1
Calling `array_find` with these arguments returns `1`.
#### json
```json
{
  "data": [
    1,
    2,
    3,
    2,
    3
  ],
  "value": 2
}
```


### Example 2
Calling `array_find` with these arguments returns `3`.
#### json
```json
{
  "data": [
    1,
    2,
    3,
    2,
    3
  ],
  "value": 2,
  "reverse": true
}
```


### Example 3
Calling `array_find` with these arguments returns `null`.
#### json
```json
{
  "data": [
    "A",
    "B",
    "C"
  ],
  "value": "b"
}
```


### Example 4
Calling `array_find` with these arguments returns `null`.
#### json
```json
{
  "data": [
    1,
    2,
    3
  ],
  "value": "2"
}
```


### Example 5
Calling `array_find` with these arguments returns `null`.
#### json
```json
{
  "data": [
    [
      1,
      2
    ],
    [
      3,
      4
    ]
  ],
  "value": [
    1,
    2
  ]
}
```


### Example 6
Calling `array_find` with these arguments returns `null`.
#### json
```json
{
  "data": [
    [
      1,
      2
    ],
    [
      3,
      4
    ]
  ],
  "value": 2
}
```


### Example 7
Calling `array_find` with these arguments returns `null`.
#### json
```json
{
  "data": [
    {
      "a": "b"
    },
    {
      "c": "d"
    }
  ],
  "value": {
    "a": "b"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Get the index for a value in an array
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  value:
    description: Any data type is allowed.
  reverse:
    type: boolean
required:
- data
- value

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_find/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_find/schema.yaml)

## Sources

* [OpenEO Processes — array_find](https://processes.openeo.org/#array_find)
* [Open-EO/openeo-processes — array_find.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_find.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_find`

