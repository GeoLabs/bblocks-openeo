
# Sqrt (Schema)

`ogc.openeo.processes.math.sqrt` *v0.1*

Square root

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sqrt`](https://processes.openeo.org/#sqrt) — *Square root*. It models the `arguments` object of a process graph node invoking `sqrt`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the square root of a real number `x`, which is equal to calculating `x` to the power of *0.5*. For negative `x`, the process returns `NaN`.

A square root of x is a number a such that *`a² = x`*. Therefore, the square root is the inverse function of a to the power of 2, but only for *a >= 0*.

No-data values are passed through.

## Source

OpenEO Processes specification: [`sqrt`](https://processes.openeo.org/#sqrt) ([openeo-processes/sqrt.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sqrt.json)).

## Examples

### Example 1
Calling `sqrt` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 2
Calling `sqrt` with these arguments returns `1`.
#### json
```json
{
  "x": 1
}
```


### Example 3
Calling `sqrt` with these arguments returns `3`.
#### json
```json
{
  "x": 9
}
```


### Example 4
Calling `sqrt` with these arguments returns `null`.
#### json
```json
{
  "x": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Square root
type: object
properties:
  x:
    type:
    - number
    - 'null'
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sqrt/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sqrt/schema.yaml)

## Sources

* [OpenEO Processes — sqrt](https://processes.openeo.org/#sqrt)
* [Open-EO/openeo-processes — sqrt.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sqrt.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/sqrt`

