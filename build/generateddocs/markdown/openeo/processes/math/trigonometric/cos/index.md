
# Cos (Schema)

`ogc.openeo.processes.math.trigonometric.cos` *v0.1*

Cosine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`cos`](https://processes.openeo.org/#cos) — *Cosine*. It models the `arguments` object of a process graph node invoking `cos`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the cosine of `x`.

Works on radians only.
No-data values are passed through.

## Source

OpenEO Processes specification: [`cos`](https://processes.openeo.org/#cos) ([openeo-processes/cos.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/cos.json)).

## Examples

### Example 1
Calling `cos` with these arguments returns `1`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Cosine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/cos/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/cos/schema.yaml)

## Sources

* [OpenEO Processes — cos](https://processes.openeo.org/#cos)
* [Open-EO/openeo-processes — cos.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/cos.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/cos`

