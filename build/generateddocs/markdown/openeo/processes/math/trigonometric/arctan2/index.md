
# Arctan2 (Schema)

`ogc.openeo.processes.math.trigonometric.arctan2` *v0.1*

Inverse tangent of two numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`arctan2`](https://processes.openeo.org/#arctan2) — *Inverse tangent of two numbers*. It models the `arguments` object of a process graph node invoking `arctan2`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc tangent of two numbers `x` and `y`. It is similar to calculating the arc tangent of *`y / x`*, except that the signs of both arguments are used to determine the quadrant of the result.

Works on radians only.
If any argument is a no-data value, the result will be the no-data value (or `null`).

## Source

OpenEO Processes specification: [`arctan2`](https://processes.openeo.org/#arctan2) ([openeo-processes/arctan2.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arctan2.json)).

## Examples

### Example 1
Calling `arctan2` with these arguments returns `0`.
#### json
```json
{
  "y": 0,
  "x": 0
}
```


### Example 2
Calling `arctan2` with these arguments returns `null`.
#### json
```json
{
  "y": null,
  "x": 1.5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverse tangent of two numbers
type: object
properties:
  y:
    type:
    - number
    - 'null'
  x:
    type:
    - number
    - 'null'
required:
- y
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arctan2/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/trigonometric/arctan2/schema.yaml)

## Sources

* [OpenEO Processes — arctan2](https://processes.openeo.org/#arctan2)
* [Open-EO/openeo-processes — arctan2.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arctan2.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/trigonometric/arctan2`

