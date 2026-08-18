
# Sinh (Schema)

`ogc.openeo.processes.math.trigonometric.sinh` *v0.1*

Hyperbolic sine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sinh`](https://processes.openeo.org/#sinh) — *Hyperbolic sine*. It models the `arguments` object of a process graph node invoking `sinh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the hyperbolic sine of `x`.

No-data values are passed through.

## Source

OpenEO Processes specification: [`sinh`](https://processes.openeo.org/#sinh) ([openeo-processes/sinh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sinh.json)).

## Examples

### Example 1
Calling `sinh` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Hyperbolic sine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/sinh/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/sinh/schema.yaml)

## Sources

* [OpenEO Processes — sinh](https://processes.openeo.org/#sinh)
* [Open-EO/openeo-processes — sinh.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sinh.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/sinh`

