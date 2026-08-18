
# Absolute (Schema)

`ogc.openeo.processes.math.absolute` *v0.1*

Absolute value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`absolute`](https://processes.openeo.org/#absolute) — *Absolute value*. It models the `arguments` object of a process graph node invoking `absolute`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the absolute value of a real number `x`, which is the "unsigned" portion of `x` and often denoted as *|x|*.

No-data values are passed through.

## Source

OpenEO Processes specification: [`absolute`](https://processes.openeo.org/#absolute) ([openeo-processes/absolute.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/absolute.json)).

## Examples

### Example 1
Calling `absolute` with these arguments returns `3.5`.
#### json
```json
{
  "x": 3.5
}
```


### Example 2
Calling `absolute` with these arguments returns `0.4`.
#### json
```json
{
  "x": -0.4
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Absolute value
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/absolute/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/absolute/schema.yaml)

## Sources

* [OpenEO Processes — absolute](https://processes.openeo.org/#absolute)
* [Open-EO/openeo-processes — absolute.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/absolute.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/absolute`

