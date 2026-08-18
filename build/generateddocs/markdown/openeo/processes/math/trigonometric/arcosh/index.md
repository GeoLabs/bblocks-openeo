
# Arcosh (Schema)

`ogc.openeo.processes.math.trigonometric.arcosh` *v0.1*

Inverse hyperbolic cosine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arcosh`](https://processes.openeo.org/#arcosh) — *Inverse hyperbolic cosine*. It models the `arguments` object of a process graph node invoking `arcosh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the inverse hyperbolic cosine of `x`. It is the inverse function of the hyperbolic cosine so that *`arcosh(cosh(x)) = x`*.

No-data values are passed through. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`arcosh`](https://processes.openeo.org/#arcosh) ([openeo-processes/arcosh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcosh.json)).

## Examples

### Example 1
Calling `arcosh` with these arguments returns `0`.
#### json
```json
{
  "x": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse hyperbolic cosine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arcosh/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arcosh/schema.yaml)

## Sources

* [OpenEO Processes — arcosh](https://processes.openeo.org/#arcosh)
* [Open-EO/openeo-processes — arcosh.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcosh.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arcosh`

