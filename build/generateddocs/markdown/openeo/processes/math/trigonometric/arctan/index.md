
# Arctan (Schema)

`ogc.openeo.processes.math.trigonometric.arctan` *v0.1*

Inverse tangent

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arctan`](https://processes.openeo.org/#arctan) — *Inverse tangent*. It models the `arguments` object of a process graph node invoking `arctan`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc tangent of `x`. The arc tangent is the inverse function of the tangent so that *`arctan(tan(x)) = x`*.

Works on radians only.
No-data values are passed through.

## Source

OpenEO Processes specification: [`arctan`](https://processes.openeo.org/#arctan) ([openeo-processes/arctan.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arctan.json)).

## Examples

### Example 1
Calling `arctan` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse tangent
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arctan/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arctan/schema.yaml)

## Sources

* [OpenEO Processes — arctan](https://processes.openeo.org/#arctan)
* [Open-EO/openeo-processes — arctan.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arctan.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arctan`

