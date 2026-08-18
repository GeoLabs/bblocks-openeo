
# Last (Schema)

`ogc.openeo.processes.arrays.last` *v0.1*

Last element

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`last`](https://processes.openeo.org/#last) — *Last element*. It models the `arguments` object of a process graph node invoking `last`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the last element of an array.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`last`](https://processes.openeo.org/#last) ([openeo-processes/last.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/last.json)).

## Examples

### Example 1
Calling `last` with these arguments returns `2`.
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
Calling `last` with these arguments returns `"B"`.
#### json
```json
{
  "data": [
    "A",
    "B",
    null
  ]
}
```


### Example 3
Calling `last` with these arguments returns `null`.
#### json
```json
{
  "data": [
    0,
    1,
    null
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Last element
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  ignore_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/last/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/last/schema.yaml)

## Sources

* [OpenEO Processes — last](https://processes.openeo.org/#last)
* [Open-EO/openeo-processes — last.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/last.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/last`

