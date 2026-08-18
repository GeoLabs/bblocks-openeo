
# Mean (Schema)

`ogc.openeo.processes.math.statistics.mean` *v0.1*

Arithmetic mean (average)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`mean`](https://processes.openeo.org/#mean) — *Arithmetic mean (average)*. It models the `arguments` object of a process graph node invoking `mean`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The arithmetic mean of an array of numbers is the quantity commonly called the average. It is defined as the sum of all elements divided by the number of elements.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`mean`](https://processes.openeo.org/#mean) ([openeo-processes/mean.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mean.json)).

## Examples

### Example 1
Calling `mean` with these arguments returns `1.5`.
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
Calling `mean` with these arguments returns `3`.
#### json
```json
{
  "data": [
    9,
    2.5,
    null,
    -2.5
  ]
}
```


### Example 3
Calling `mean` with these arguments returns `null`.
#### json
```json
{
  "data": [
    1,
    null
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Arithmetic mean (average)
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/mean/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/mean/schema.yaml)

## Sources

* [OpenEO Processes — mean](https://processes.openeo.org/#mean)
* [Open-EO/openeo-processes — mean.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mean.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/mean`

