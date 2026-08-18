
# Variance (Schema)

`ogc.openeo.processes.math.statistics.variance` *v0.1*

Variance

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`variance`](https://processes.openeo.org/#variance) — *Variance*. It models the `arguments` object of a process graph node invoking `variance`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the sample variance of an array of numbers by calculating the square of the standard deviation (see `sd()`). It is defined to be the expectation of the squared deviation of a random variable from its expected value. Basically, it measures how far the numbers in the array are spread out from their average value.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`variance`](https://processes.openeo.org/#variance) ([openeo-processes/variance.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/variance.json)).

## Examples

### Example 1
Calling `variance` with these arguments returns `4`.
#### json
```json
{
  "data": [
    -1,
    1,
    3
  ]
}
```


### Example 2
Calling `variance` with these arguments returns `1.1`.
#### json
```json
{
  "data": [
    2,
    3,
    3,
    null,
    4,
    4,
    5
  ]
}
```


### Example 3
Calling `variance` with these arguments returns `null`.
#### json
```json
{
  "data": [
    -1,
    1,
    null,
    3
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Variance
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/variance/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/variance/schema.yaml)

## Sources

* [OpenEO Processes — variance](https://processes.openeo.org/#variance)
* [Open-EO/openeo-processes — variance.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/variance.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/variance`

