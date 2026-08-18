
# First (Schema)

`ogc.openeo.processes.arrays.first` *v0.1*

First element

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`first`](https://processes.openeo.org/#first) — *First element*. It models the `arguments` object of a process graph node invoking `first`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the first element of an array.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`first`](https://processes.openeo.org/#first) ([openeo-processes/first.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/first.json)).

## Examples

### Example 1
Calling `first` with these arguments returns `1`.
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
Calling `first` with these arguments returns `"A"`.
#### json
```json
{
  "data": [
    null,
    "A",
    "B"
  ]
}
```


### Example 3
Calling `first` with these arguments returns `null`.
#### json
```json
{
  "data": [
    null,
    2,
    3
  ],
  "ignore_nodata": false
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: First element
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/first/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/first/schema.yaml)

## Sources

* [OpenEO Processes — first](https://processes.openeo.org/#first)
* [Open-EO/openeo-processes — first.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/first.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/first`

