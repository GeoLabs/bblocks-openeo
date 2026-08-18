
# Arccos (Schema)

`ogc.openeo.processes.math.trigonometric.arccos` *v0.1*

Inverse cosine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arccos`](https://processes.openeo.org/#arccos) — *Inverse cosine*. It models the `arguments` object of a process graph node invoking `arccos`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc cosine of `x`. The arc cosine is the inverse function of the cosine so that *`arccos(cos(x)) = x`*.

Works on radians only.
No-data values are passed through. `NaN` is returned for values < -1 and > 1.

## Source

OpenEO Processes specification: [`arccos`](https://processes.openeo.org/#arccos) ([openeo-processes/arccos.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arccos.json)).

## Examples

### Example 1
Calling `arccos` with these arguments returns `0`.
#### json
```json
{
  "x": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse cosine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arccos/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arccos/schema.yaml)

## Sources

* [OpenEO Processes — arccos](https://processes.openeo.org/#arccos)
* [Open-EO/openeo-processes — arccos.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arccos.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arccos`

