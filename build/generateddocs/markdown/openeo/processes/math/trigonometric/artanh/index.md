
# Artanh (Schema)

`ogc.openeo.processes.math.trigonometric.artanh` *v0.1*

Inverse hyperbolic tangent

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`artanh`](https://processes.openeo.org/#artanh) — *Inverse hyperbolic tangent*. It models the `arguments` object of a process graph node invoking `artanh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the inverse hyperbolic tangent of `x`. It is the inverse function of the hyperbolic tangent so that *`artanh(tanh(x)) = x`*.

No-data values are passed through. `NaN` is returned for values outside of the allowed range. The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, `x` = 1 results in +infinity and `x` = 0 results in -infinity. Otherwise, an exception is thrown.

## Source

OpenEO Processes specification: [`artanh`](https://processes.openeo.org/#artanh) ([openeo-processes/artanh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/artanh.json)).

## Examples

### Example 1
Calling `artanh` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse hyperbolic tangent
type: object
properties:
  x:
    type:
    - number
    - 'null'
    minimumExclusive: -1
    maximumExclusive: 1
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/artanh/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/artanh/schema.yaml)

## Sources

* [OpenEO Processes — artanh](https://processes.openeo.org/#artanh)
* [Open-EO/openeo-processes — artanh.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/artanh.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/artanh`

