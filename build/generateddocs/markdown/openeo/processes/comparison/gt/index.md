
# GT (Schema)

`ogc.openeo.processes.comparison.gt` *v0.1*

Greater than comparison

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`gt`](https://processes.openeo.org/#gt) — *Greater than comparison*. It models the `arguments` object of a process graph node invoking `gt`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Compares whether `x` is strictly greater than `y`.

**Remarks:**

* If any operand is a no-data value, the result will be the no-data value (or `null`).
* The comparison of `NaN` (not a number) follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229).
* If any operand is not the data type `number`, the process returns `false`.
* Temporal strings are normal strings. To compare temporal strings as dates/times, use `date_difference()`.

## Source

OpenEO Processes specification: [`gt`](https://processes.openeo.org/#gt) ([openeo-processes/gt.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/gt.json)).

## Examples

### Example 1
Calling `gt` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```


### Example 2
Calling `gt` with these arguments returns `false`.
#### json
```json
{
  "x": 0,
  "y": 0
}
```


### Example 3
Calling `gt` with these arguments returns `true`.
#### json
```json
{
  "x": 2,
  "y": 1
}
```


### Example 4
Calling `gt` with these arguments returns `true`.
#### json
```json
{
  "x": -0.5,
  "y": -0.6
}
```


### Example 5
Calling `gt` with these arguments returns `false`.
#### json
```json
{
  "x": "2018-01-02T00:00:00Z",
  "y": "2018-01-01T00:00:00Z"
}
```


### Example 6
Calling `gt` with these arguments returns `false`.
#### json
```json
{
  "x": true,
  "y": 0
}
```


### Example 7
Calling `gt` with these arguments returns `false`.
#### json
```json
{
  "x": true,
  "y": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Greater than comparison
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/gt/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/gt/schema.yaml)

## Sources

* [OpenEO Processes — gt](https://processes.openeo.org/#gt)
* [Open-EO/openeo-processes — gt.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/gt.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/gt`

