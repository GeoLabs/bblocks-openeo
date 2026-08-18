
# Array contains (Schema)

`ogc.openeo.processes.arrays.array_contains` *v0.1*

Check whether the array contains a given value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_contains`](https://processes.openeo.org/#array_contains) — *Check whether the array contains a given value*. It models the `arguments` object of a process graph node invoking `array_contains`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the array specified for `data` contains the value specified in `value`. Returns `true` if there's a match, otherwise `false`.

**Remarks:**

* To get the index or the label of the value found, use `array_find()`.
* All definitions for the process `eq()` regarding the comparison of values apply here as well. A no-data return value from `eq()` is handled as `false` (no match).
* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*.
* An integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`. Still, this process may return unexpectedly `false` when comparing floating-point numbers due to floating-point inaccuracy in machine-based computation.
* Temporal strings are treated as normal strings and MUST NOT be interpreted.

See the examples to check for no-data values.

## Source

OpenEO Processes specification: [`array_contains`](https://processes.openeo.org/#array_contains) ([openeo-processes/array_contains.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_contains.json)).

## Examples

### Example 1
Calling `array_contains` with these arguments returns `true`.
#### json
```json
{
  "data": [
    1,
    2,
    3
  ],
  "value": 2
}
```


### Example 2
Calling `array_contains` with these arguments returns `false`.
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


### Example 3
Calling `array_contains` with these arguments returns `false`.
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


### Example 4
Calling `array_contains` with these arguments returns `false`.
#### json
```json
{
  "data": [
    1,
    2,
    null
  ],
  "value": null
}
```


### Example 5
Calling `array_contains` with these arguments returns `false`.
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

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Check whether the array contains a given value
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  value:
    type:
    - number
    - boolean
    - string
    - 'null'
required:
- data
- value

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_contains/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_contains/schema.yaml)

## Sources

* [OpenEO Processes — array_contains](https://processes.openeo.org/#array_contains)
* [Open-EO/openeo-processes — array_contains.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_contains.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_contains`

