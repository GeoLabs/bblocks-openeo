
# Max (Schema)

`ogc.openeo.processes.math.max` *v0.1*

Maximum value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`max`](https://processes.openeo.org/#max) — *Maximum value*. It models the `arguments` object of a process graph node invoking `max`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the largest value of an array of numbers, which is equal to the first element of a sorted (i.e., ordered) version of the array.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`max`](https://processes.openeo.org/#max) ([openeo-processes/max.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/max.json)).

## Examples

### Example 1
Calling `max` with these arguments returns `3`.
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
Calling `max` with these arguments returns `5`.
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
Calling `max` with these arguments returns `null`.
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

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Maximum value
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/max/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/max/schema.yaml)

## Sources

* [OpenEO Processes — max](https://processes.openeo.org/#max)
* [Open-EO/openeo-processes — max.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/max.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/max`

