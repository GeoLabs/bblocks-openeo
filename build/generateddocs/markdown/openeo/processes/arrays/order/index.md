
# Order (Schema)

`ogc.openeo.processes.arrays.order` *v0.1*

Get the order of array elements

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`order`](https://processes.openeo.org/#order) — *Get the order of array elements*. It models the `arguments` object of a process graph node invoking `order`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the ranked (sorted) element positions in the original list (i.e., a permutation), either in ascending or descending order. The process `rearrange()` allows sorting the data based on the computed permutation.

**Remarks:**

* The positions in the result are zero-based.
* The ordering of ties is implementation-dependent.
* Temporal strings can *not* be compared based on their string representation due to the time zone/time-offset representations.

## Source

OpenEO Processes specification: [`order`](https://processes.openeo.org/#order) ([openeo-processes/order.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/order.json)).

## Examples

### Example 1
Calling `order` with these arguments returns `[1, 2, 8, 5, 0, 4, 7, 9, 10]`.
#### json
```json
{
  "data": [
    6,
    -1,
    2,
    null,
    7,
    4,
    null,
    8,
    3,
    9,
    9
  ]
}
```


### Example 2
Calling `order` with these arguments returns `[1, 2, 8, 5, 0, 4, 7, 9, 10, 3, 6]`.
#### json
```json
{
  "data": [
    6,
    -1,
    2,
    null,
    7,
    4,
    null,
    8,
    3,
    9,
    9
  ],
  "nodata": true
}
```


### Example 3
Calling `order` with these arguments returns `[9, 10, 7, 4, 0, 5, 8, 2, 1, 3, 6]`.
#### json
```json
{
  "data": [
    6,
    -1,
    2,
    null,
    7,
    4,
    null,
    8,
    3,
    9,
    9
  ],
  "asc": false,
  "nodata": true
}
```


### Example 4
Calling `order` with these arguments returns `[3, 6, 9, 10, 7, 4, 0, 5, 8, 2, 1]`.
#### json
```json
{
  "data": [
    6,
    -1,
    2,
    null,
    7,
    4,
    null,
    8,
    3,
    9,
    9
  ],
  "asc": false,
  "nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Get the order of array elements
type: object
properties:
  data:
    type: array
    items:
      anyOf:
      - type: number
      - type: 'null'
      - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
      - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
  asc:
    type: boolean
  nodata:
    type:
    - boolean
    - 'null'
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/order/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/order/schema.yaml)

## Sources

* [OpenEO Processes — order](https://processes.openeo.org/#order)
* [Open-EO/openeo-processes — order.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/order.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/order`

