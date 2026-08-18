
# Arsinh (Schema)

`ogc.openeo.processes.math.trigonometric.arsinh` *v0.1*

Inverse hyperbolic sine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arsinh`](https://processes.openeo.org/#arsinh) — *Inverse hyperbolic sine*. It models the `arguments` object of a process graph node invoking `arsinh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the inverse hyperbolic sine of `x`. It is the inverse function of the hyperbolic sine so that *`arsinh(sinh(x)) = x`*.

No-data values are passed through.

## Source

OpenEO Processes specification: [`arsinh`](https://processes.openeo.org/#arsinh) ([openeo-processes/arsinh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arsinh.json)).

## Examples

### Example 1
Calling `arsinh` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse hyperbolic sine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arsinh/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arsinh/schema.yaml)

## Sources

* [OpenEO Processes — arsinh](https://processes.openeo.org/#arsinh)
* [Open-EO/openeo-processes — arsinh.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arsinh.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arsinh`

