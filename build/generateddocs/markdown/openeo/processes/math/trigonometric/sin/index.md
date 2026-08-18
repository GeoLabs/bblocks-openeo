
# Sin (Schema)

`ogc.openeo.processes.math.trigonometric.sin` *v0.1*

Sine

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sin`](https://processes.openeo.org/#sin) — *Sine*. It models the `arguments` object of a process graph node invoking `sin`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the sine of `x`.

Works on radians only.
No-data values are passed through.

## Source

OpenEO Processes specification: [`sin`](https://processes.openeo.org/#sin) ([openeo-processes/sin.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sin.json)).

## Examples

### Example 1
Calling `sin` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Sine
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/sin/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/sin/schema.yaml)

## Sources

* [OpenEO Processes — sin](https://processes.openeo.org/#sin)
* [Open-EO/openeo-processes — sin.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sin.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/sin`

