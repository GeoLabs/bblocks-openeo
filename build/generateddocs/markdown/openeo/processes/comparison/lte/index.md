
# LTE (Schema)

`ogc.openeo.processes.comparison.lte` *v0.1*

Less than or equal to comparison

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`lte`](https://processes.openeo.org/#lte) — *Less than or equal to comparison*. It models the `arguments` object of a process graph node invoking `lte`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is less than or equal to `y`.

**Remarks:**

* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* If the operands are not equal (see process `eq()`) and any of them is not the data type `number`, the process returns `false`.
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`lte`](https://processes.openeo.org/#lte) ([openeo-processes/lte.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/lte.json)).

## Examples

### Example 1
Calling `lte` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```


### Example 2
Calling `lte` with these arguments returns `true`.
#### json
```json
{
  "x": 0,
  "y": 0
}
```


### Example 3
Calling `lte` with these arguments returns `true`.
#### json
```json
{
  "x": 1,
  "y": 2
}
```


### Example 4
Calling `lte` with these arguments returns `false`.
#### json
```json
{
  "x": -0.5,
  "y": -0.6
}
```


### Example 5
Calling `lte` with these arguments returns `false`.
#### json
```json
{
  "x": "2018-01-01T00:00:00Z",
  "y": "2018-01-01T00:00:00+00:00"
}
```


### Example 6
Calling `lte` with these arguments returns `false`.
#### json
```json
{
  "x": false,
  "y": true
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Less than or equal to comparison
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
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/lte/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/lte/schema.yaml)

## Sources

* [OpenEO Processes — lte](https://processes.openeo.org/#lte)
* [Open-EO/openeo-processes — lte.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/lte.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/lte`

