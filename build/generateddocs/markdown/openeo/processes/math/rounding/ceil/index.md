
# Ceil (Schema)

`ogc.openeo.processes.math.rounding.ceil` *v0.1*

Round fractions up

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`ceil`](https://processes.openeo.org/#ceil) — *Round fractions up*. It models the `arguments` object of a process graph node invoking `ceil`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The least integer greater than or equal to the number `x`.

No-data values are passed through.

## Source

OpenEO Processes specification: [`ceil`](https://processes.openeo.org/#ceil) ([openeo-processes/ceil.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ceil.json)).

## Examples

### Example 1
Calling `ceil` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 2
Calling `ceil` with these arguments returns `4`.
#### json
```json
{
  "x": 3.5
}
```


### Example 3
Calling `ceil` with these arguments returns `0`.
#### json
```json
{
  "x": -0.4
}
```


### Example 4
Calling `ceil` with these arguments returns `-3`.
#### json
```json
{
  "x": -3.5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Round fractions up
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/ceil/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/ceil/schema.yaml)

## Sources

* [OpenEO Processes — ceil](https://processes.openeo.org/#ceil)
* [Open-EO/openeo-processes — ceil.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ceil.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/rounding/ceil`

