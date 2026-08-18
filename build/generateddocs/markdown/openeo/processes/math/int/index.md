
# Int (Schema)

`ogc.openeo.processes.math.int` *v0.1*

Integer part of a number

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`int`](https://processes.openeo.org/#int) — *Integer part of a number*. It models the `arguments` object of a process graph node invoking `int`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The integer part of the real number `x`.

This process is *not* an alias for the `floor()` process as defined by some mathematicians, see the examples for negative numbers in both processes for differences.

No-data values are passed through.

## Source

OpenEO Processes specification: [`int`](https://processes.openeo.org/#int) ([openeo-processes/int.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/int.json)).

## Examples

### Example 1
Calling `int` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 2
Calling `int` with these arguments returns `3`.
#### json
```json
{
  "x": 3.5
}
```


### Example 3
Calling `int` with these arguments returns `0`.
#### json
```json
{
  "x": -0.4
}
```


### Example 4
Calling `int` with these arguments returns `-3`.
#### json
```json
{
  "x": -3.5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Integer part of a number
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/int/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/int/schema.yaml)

## Sources

* [OpenEO Processes — int](https://processes.openeo.org/#int)
* [Open-EO/openeo-processes — int.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/int.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/int`

