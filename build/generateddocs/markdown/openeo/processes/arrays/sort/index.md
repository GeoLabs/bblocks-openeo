
# Sort (Schema)

`ogc.openeo.processes.arrays.sort` *v0.1*

Sort data

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sort`](https://processes.openeo.org/#sort) — *Sort data*. It models the `arguments` object of a process graph node invoking `sort`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Sorts an array into ascending (default) or descending order.

**Remarks:**

* The ordering of ties is implementation-dependent.
* Temporal strings can *not* be compared based on their string representation due to the time zone/time-offset representations.

## Source

OpenEO Processes specification: [`sort`](https://processes.openeo.org/#sort) ([openeo-processes/sort.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sort.json)).

## Examples

### Example 1
Calling `sort` with these arguments returns `[-1, 2, 3, 4, 6, 7, 8, 9, 9]`.
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
Calling `sort` with these arguments returns `[9, 9, 8, 7, 6, 4, 3, 2, -1, null, null]`.
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

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Sort data
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/sort/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/sort/schema.yaml)

## Sources

* [OpenEO Processes — sort](https://processes.openeo.org/#sort)
* [Open-EO/openeo-processes — sort.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sort.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/sort`

