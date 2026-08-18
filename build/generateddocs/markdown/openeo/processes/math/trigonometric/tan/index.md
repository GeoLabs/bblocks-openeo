
# Tan (Schema)

`ogc.openeo.processes.math.trigonometric.tan` *v0.1*

Tangent

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`tan`](https://processes.openeo.org/#tan) — *Tangent*. It models the `arguments` object of a process graph node invoking `tan`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the tangent of `x`. The tangent is defined to be the sine of x divided by the cosine of x.

Works on radians only.
No-data values are passed through.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, *`tan(pi()/2 + multipliy(pi(), n))`* with `n` being any integer results in ±infinity. -infinity for negative values passed to `tan`, +infinity otherwise. If the processing environment does not supports it, an exception is thrown.

## Source

OpenEO Processes specification: [`tan`](https://processes.openeo.org/#tan) ([openeo-processes/tan.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/tan.json)).

## Examples

### Example 1
Calling `tan` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Tangent
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/tan/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/tan/schema.yaml)

## Sources

* [OpenEO Processes — tan](https://processes.openeo.org/#tan)
* [Open-EO/openeo-processes — tan.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/tan.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/tan`

