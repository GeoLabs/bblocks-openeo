
# Tanh (Schema)

`ogc.openeo.processes.math.trigonometric.tanh` *v0.1*

Hyperbolic tangent

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`tanh`](https://processes.openeo.org/#tanh) — *Hyperbolic tangent*. It models the `arguments` object of a process graph node invoking `tanh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the hyperbolic tangent of `x`. The tangent is defined to be the hyperbolic sine of x divided by the hyperbolic cosine of x.

No-data values are passed through.

## Source

OpenEO Processes specification: [`tanh`](https://processes.openeo.org/#tanh) ([openeo-processes/tanh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/tanh.json)).

## Examples

### Example 1
Calling `tanh` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Hyperbolic tangent
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/tanh/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/tanh/schema.yaml)

## Sources

* [OpenEO Processes — tanh](https://processes.openeo.org/#tanh)
* [Open-EO/openeo-processes — tanh.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/tanh.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/tanh`

