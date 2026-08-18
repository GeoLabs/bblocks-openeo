
# Extrema (Schema)

`ogc.openeo.processes.math.statistics.extrema` *v0.1*

Minimum and maximum values

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`extrema`](https://processes.openeo.org/#extrema) — *Minimum and maximum values*. It models the `arguments` object of a process graph node invoking `extrema`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Two element array containing the minimum and the maximum values of `data`.

This process is basically an alias for calling both `min()` and `max()`, but may be implemented more performant by back-ends as it only needs to iterate over the data once instead of twice.

## Source

OpenEO Processes specification: [`extrema`](https://processes.openeo.org/#extrema) ([openeo-processes/extrema.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/extrema.json)).

## Examples

### Example 1
Calling `extrema` with these arguments returns `[0, 3]`.
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
Calling `extrema` with these arguments returns `[-0.7, 5]`.
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
Calling `extrema` with these arguments returns `[null, null]`.
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
description: Minimum and maximum values
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/extrema/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/statistics/extrema/schema.yaml)

## Sources

* [OpenEO Processes — extrema](https://processes.openeo.org/#extrema)
* [Open-EO/openeo-processes — extrema.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/extrema.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/statistics/extrema`

