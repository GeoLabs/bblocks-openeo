
# Arcsin (Schema)

`ogc.openeo.processes.math.trigonometric.arcsin` *v0.1*

Inverse sine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arcsin`](https://processes.openeo.org/#arcsin) — *Inverse sine*. It models the `arguments` object of a process graph node invoking `arcsin`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc sine of `x`. The arc sine is the inverse function of the sine so that *`arcsin(sin(x)) = x`*.

Works on radians only.
No-data values are passed through. `NaN` is returned for values < -1 and > 1.

## Source

OpenEO Processes specification: [`arcsin`](https://processes.openeo.org/#arcsin) ([openeo-processes/arcsin.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcsin.json)).

## Examples

### Example 1
Calling `arcsin` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse sine
type: object
properties:
  x:
    type:
    - number
    - 'null'
    minimum: -1
    maximum: 1
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arcsin/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arcsin/schema.yaml)

## Sources

* [OpenEO Processes — arcsin](https://processes.openeo.org/#arcsin)
* [Open-EO/openeo-processes — arcsin.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcsin.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arcsin`

