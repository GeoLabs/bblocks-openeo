
# Min (Schema)

`ogc.openeo.processes.math.min` *v0.1*

Minimum value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`min`](https://processes.openeo.org/#min) — *Minimum value*. It models the `arguments` object of a process graph node invoking `min`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the smallest value of an array of numbers, which is equal to the last element of a sorted (i.e., ordered) version of the array.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`min`](https://processes.openeo.org/#min) ([openeo-processes/min.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/min.json)).

## Examples

### Example 1
Calling `min` with these arguments returns `0`.
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


### Example 2
Calling `min` with these arguments returns `-0.7`.
#### json
```json
{
  "data": [
    5,
    2.5,
    null,
    -0.7
  ]
}
```


### Example 3
Calling `min` with these arguments returns `null`.
#### json
```json
{
  "data": [
    1,
    0,
    3,
    null,
    2
  ],
  "ignore_nodata": false
}
```


### Example 4
Calling `min` with these arguments returns `null`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Minimum value
type: object
properties:
  data:
    type: array
    items:
      type:
      - number
      - 'null'
  ignore_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/min/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/min/schema.yaml)

## Sources

* [OpenEO Processes — min](https://processes.openeo.org/#min)
* [Open-EO/openeo-processes — min.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/min.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/min`

