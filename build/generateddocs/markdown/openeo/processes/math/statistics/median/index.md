
# Median (Schema)

`ogc.openeo.processes.math.statistics.median` *v0.1*

Statistical median

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`median`](https://processes.openeo.org/#median) — *Statistical median*. It models the `arguments` object of a process graph node invoking `median`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The statistical median of an array of numbers is the value separating the higher half from the lower half of the data.

An array with solely no-data values returns the no-data value (or `null`).

**Remarks:**

* For symmetric arrays, the result is equal to the `mean()`.
* The median can also be calculated by computing the `quantiles()` with a probability of *0.5*.

## Source

OpenEO Processes specification: [`median`](https://processes.openeo.org/#median) ([openeo-processes/median.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/median.json)).

## Examples

### Example 1
Calling `median` with these arguments returns `6`.
#### json
```json
{
  "data": [
    1,
    3,
    3,
    6,
    7,
    8,
    9
  ]
}
```


### Example 2
Calling `median` with these arguments returns `4.5`.
#### json
```json
{
  "data": [
    1,
    2,
    3,
    4,
    5,
    6,
    8,
    9
  ]
}
```


### Example 3
Calling `median` with these arguments returns `-0.5`.
#### json
```json
{
  "data": [
    -1,
    -0.5,
    null,
    1
  ]
}
```


### Example 4
Calling `median` with these arguments returns `null`.
#### json
```json
{
  "data": [
    -1,
    0,
    null,
    1
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Statistical median
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/median/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/median/schema.yaml)

## Sources

* [OpenEO Processes — median](https://processes.openeo.org/#median)
* [Open-EO/openeo-processes — median.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/median.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/median`

