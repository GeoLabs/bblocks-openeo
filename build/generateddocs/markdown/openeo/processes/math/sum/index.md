
# Sum (Schema)

`ogc.openeo.processes.math.sum` *v0.1*

Compute the sum by adding up numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sum`](https://processes.openeo.org/#sum) — *Compute the sum by adding up numbers*. It models the `arguments` object of a process graph node invoking `sum`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Sums up all elements in a sequential array of numbers and returns the computed sum.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`sum`](https://processes.openeo.org/#sum) ([openeo-processes/sum.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sum.json)).

## Examples

### Example 1
Calling `sum` with these arguments returns `6`.
#### json
```json
{
  "data": [
    5,
    1
  ]
}
```


### Example 2
Calling `sum` with these arguments returns `4.5`.
#### json
```json
{
  "data": [
    -2,
    4,
    2.5
  ]
}
```


### Example 3
Calling `sum` with these arguments returns `null`.
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


### Example 4
Calling `sum` with these arguments returns `100`.
#### json
```json
{
  "data": [
    100
  ]
}
```


### Example 5
Calling `sum` with these arguments returns `null`.
#### json
```json
{
  "data": [
    null
  ],
  "ignore_nodata": false
}
```


### Example 6
Calling `sum` with these arguments returns `null`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Compute the sum by adding up numbers
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sum/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sum/schema.yaml)

## Sources

* [OpenEO Processes — sum](https://processes.openeo.org/#sum)
* [Open-EO/openeo-processes — sum.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sum.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/sum`

