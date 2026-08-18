
# EQ (Schema)

`ogc.openeo.processes.texts.eq` *v0.1*

Equal to comparison

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`eq`](https://processes.openeo.org/#eq) — *Equal to comparison*. It models the `arguments` object of a process graph node invoking `eq`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is strictly equal to `y`.

**Remarks:**

* Data types MUST be checked strictly. For example, a string with the content *1* is not equal to the number *1*. Nevertheless, an integer *1* is equal to a floating-point number *1.0* as `integer` is a sub-type of `number`.
* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`eq`](https://processes.openeo.org/#eq) ([openeo-processes/eq.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/eq.json)).

## Examples

### Example 1
Calling `eq` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```


### Example 2
Calling `eq` with these arguments returns `true`.
#### json
```json
{
  "x": 1,
  "y": 1
}
```


### Example 3
Calling `eq` with these arguments returns `false`.
#### json
```json
{
  "x": 1,
  "y": "1"
}
```


### Example 4
Calling `eq` with these arguments returns `false`.
#### json
```json
{
  "x": 0,
  "y": false
}
```


### Example 5
Calling `eq` with these arguments returns `false`.
#### json
```json
{
  "x": 1.02,
  "y": 1,
  "delta": 0.01
}
```


### Example 6
Calling `eq` with these arguments returns `true`.
#### json
```json
{
  "x": -1,
  "y": -1.001,
  "delta": 0.01
}
```


### Example 7
Calling `eq` with these arguments returns `true`.
#### json
```json
{
  "x": 115,
  "y": 110,
  "delta": 10
}
```


### Example 8
Calling `eq` with these arguments returns `false`.
#### json
```json
{
  "x": "Test",
  "y": "test"
}
```


### Example 9
Calling `eq` with these arguments returns `true`.
#### json
```json
{
  "x": "Test",
  "y": "test",
  "case_sensitive": false
}
```


### Example 10
Calling `eq` with these arguments returns `true`.
#### json
```json
{
  "x": "\u00c4",
  "y": "\u00e4",
  "case_sensitive": false
}
```


### Example 11
Calling `eq` with these arguments returns `false`.
#### json
```json
{
  "x": "2018-01-01T00:00:00Z",
  "y": "2018-01-01T00:00:00+00:00"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Equal to comparison
type: object
properties:
  x:
    type:
    - number
    - boolean
    - string
    - 'null'
  y:
    type:
    - number
    - boolean
    - string
    - 'null'
  delta:
    type:
    - number
    - 'null'
    minimumExclusive: 0
  case_sensitive:
    type: boolean
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/eq/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/eq/schema.yaml)

## Sources

* [OpenEO Processes — eq](https://processes.openeo.org/#eq)
* [Open-EO/openeo-processes — eq.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/eq.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/texts/eq`

