
# Quantiles (Schema)

`ogc.openeo.processes.math.statistics.quantiles` *v0.1*

Quantiles

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`quantiles`](https://processes.openeo.org/#quantiles) — *Quantiles*. It models the `arguments` object of a process graph node invoking `quantiles`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Calculates quantiles, which are cut points dividing the range of a sample distribution into either

1. intervals corresponding to the given probabilities *or*
2. equal-sized intervals (q-quantiles).

Either the parameter `probabilities` or `q` must be specified, otherwise the `QuantilesParameterMissing` exception is thrown. If both parameters are set the `QuantilesParameterConflict` exception is thrown.

Sample quantiles can be computed with several different algorithms. Hyndman and Fan (1996) have concluded on nine different types, which are commonly implemented in statistical software packages. This process is implementing type 7, which is implemented widely and often also the default type (e.g. in Excel, Julia, Python, R and S).

## Exceptions

- `QuantilesParameterMissing`: The process `quantiles` requires either the `probabilities` or `q` parameter to be set.
- `QuantilesParameterConflict`: The process `quantiles` only allows that either the `probabilities` or the `q` parameter is set.
- `AscendingProbabilitiesRequired`: The values passed for parameter `probabilities` must be sorted in ascending order.

## Source

OpenEO Processes specification: [`quantiles`](https://processes.openeo.org/#quantiles) ([openeo-processes/quantiles.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/quantiles.json)).

## Examples

### Example 1
Calling `quantiles` with these arguments returns `[2.07, 2.14, 2.28, 2.7, 3.4, 4.5]`.
#### json
```json
{
  "data": [
    2,
    4,
    4,
    4,
    5,
    5,
    7,
    9
  ],
  "probabilities": [
    0.005,
    0.01,
    0.02,
    0.05,
    0.1,
    0.5
  ]
}
```


### Example 2
Calling `quantiles` with these arguments returns `[4, 4.5, 5.5]`.
#### json
```json
{
  "data": [
    2,
    4,
    4,
    4,
    5,
    5,
    7,
    9
  ],
  "probabilities": 4
}
```


### Example 3
Calling `quantiles` with these arguments returns `[-0.5]`.
#### json
```json
{
  "data": [
    -1,
    -0.5,
    null,
    1
  ],
  "probabilities": 2
}
```


### Example 4
Calling `quantiles` with these arguments returns `[null, null, null]`.
#### json
```json
{
  "data": [
    -1,
    -0.5,
    null,
    1
  ],
  "probabilities": 4,
  "ignore_nodata": false
}
```


### Empty array
Calling `quantiles` with these arguments returns `[null, null]`.
#### json
```json
{
  "data": [],
  "probabilities": [
    0.1,
    0.5
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Quantiles
type: object
properties:
  data:
    type: array
    items:
      type:
      - number
      - 'null'
  probabilities:
    anyOf:
    - title: List of probabilities
      type: array
      uniqueItems: true
      items:
        type: number
        minimum: 0
        maximum: 1
    - title: Number of intervals (q-quantiles)
      type: integer
      minimum: 2
  q:
    type: integer
    minimum: 2
    deprecated: true
  ignore_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/quantiles/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/quantiles/schema.yaml)

## Sources

* [OpenEO Processes — quantiles](https://processes.openeo.org/#quantiles)
* [Open-EO/openeo-processes — quantiles.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/quantiles.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/quantiles`

