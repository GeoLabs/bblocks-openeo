
# Rearrange (Schema)

`ogc.openeo.processes.arrays.rearrange` *v0.1*

Sort an array based on a permutation

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`rearrange`](https://processes.openeo.org/#rearrange) — *Sort an array based on a permutation*. It models the `arguments` object of a process graph node invoking `rearrange`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Rearranges an array based on a ranked list of element positions in the original list (i.e., a permutation). The positions must be zero-based. The process `order()` can compute such a permutation.

## Source

OpenEO Processes specification: [`rearrange`](https://processes.openeo.org/#rearrange) ([openeo-processes/rearrange.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rearrange.json)).

## Examples

### Reverse a list
Calling `rearrange` with these arguments returns `[3, 4, 5]`.
#### json
```json
{
  "data": [
    5,
    4,
    3
  ],
  "order": [
    2,
    1,
    0
  ]
}
```


### Remove two elements
Calling `rearrange` with these arguments returns `[4, 2]`.
#### json
```json
{
  "data": [
    5,
    4,
    3,
    2
  ],
  "order": [
    1,
    3
  ]
}
```


### Swap two elements
Calling `rearrange` with these arguments returns `[5, 3, 4, 2]`.
#### json
```json
{
  "data": [
    5,
    4,
    3,
    2
  ],
  "order": [
    0,
    2,
    1,
    3
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Sort an array based on a permutation
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  order:
    type: array
    items:
      type: integer
      minimum: 0
required:
- data
- order

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/rearrange/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/rearrange/schema.yaml)

## Sources

* [OpenEO Processes — rearrange](https://processes.openeo.org/#rearrange)
* [Open-EO/openeo-processes — rearrange.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rearrange.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/rearrange`

