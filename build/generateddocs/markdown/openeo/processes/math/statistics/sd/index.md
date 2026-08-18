
# Sd (Schema)

`ogc.openeo.processes.math.statistics.sd` *v0.1*

Standard deviation

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sd`](https://processes.openeo.org/#sd) — *Standard deviation*. It models the `arguments` object of a process graph node invoking `sd`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the sample standard deviation, which quantifies the amount of variation of an array of numbers. It is defined to be the square root of the corresponding variance (see `variance()`).

A low standard deviation indicates that the values tend to be close to the expected value, while a high standard deviation indicates that the values are spread out over a wider range.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`sd`](https://processes.openeo.org/#sd) ([openeo-processes/sd.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sd.json)).

## Examples

### Example 1
Calling `sd` with these arguments returns `2`.
#### json
```json
{
  "data": [
    -1,
    1,
    3,
    null
  ]
}
```


### Example 2
Calling `sd` with these arguments returns `null`.
#### json
```json
{
  "data": [
    -1,
    1,
    3,
    null
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Standard deviation
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/sd/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/sd/schema.yaml)

## Sources

* [OpenEO Processes — sd](https://processes.openeo.org/#sd)
* [Open-EO/openeo-processes — sd.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sd.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/sd`

