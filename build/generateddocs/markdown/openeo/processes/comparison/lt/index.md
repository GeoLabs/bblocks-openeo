
# LT (Schema)

`ogc.openeo.processes.comparison.lt` *v0.1*

Less than comparison

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`lt`](https://processes.openeo.org/#lt) — *Less than comparison*. It models the `arguments` object of a process graph node invoking `lt`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is strictly less than `y`.

**Remarks:**

* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* If any operand is not the data type `number`, the process returns `false`.
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`lt`](https://processes.openeo.org/#lt) ([openeo-processes/lt.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/lt.json)).

## Examples

### Example 1
Calling `lt` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```


### Example 2
Calling `lt` with these arguments returns `false`.
#### json
```json
{
  "x": 0,
  "y": 0
}
```


### Example 3
Calling `lt` with these arguments returns `true`.
#### json
```json
{
  "x": 1,
  "y": 2
}
```


### Example 4
Calling `lt` with these arguments returns `false`.
#### json
```json
{
  "x": -0.5,
  "y": -0.6
}
```


### Example 5
Calling `lt` with these arguments returns `false`.
#### json
```json
{
  "x": "2018-01-01T00:00:00Z",
  "y": "2018-01-02T00:00:00Z"
}
```


### Example 6
Calling `lt` with these arguments returns `false`.
#### json
```json
{
  "x": 0,
  "y": true
}
```


### Example 7
Calling `lt` with these arguments returns `false`.
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
description: Less than comparison
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/lt/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/lt/schema.yaml)

## Sources

* [OpenEO Processes — lt](https://processes.openeo.org/#lt)
* [Open-EO/openeo-processes — lt.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/lt.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/lt`

