
# Floor (Schema)

`ogc.openeo.processes.math.rounding.floor` *v0.1*

Round fractions down

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`floor`](https://processes.openeo.org/#floor) — *Round fractions down*. It models the `arguments` object of a process graph node invoking `floor`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The greatest integer less than or equal to the number `x`.

This process is *not* an alias for the `int()` process as defined by some mathematicians, see the examples for negative numbers in both processes for differences.

No-data values are passed through.

## Source

OpenEO Processes specification: [`floor`](https://processes.openeo.org/#floor) ([openeo-processes/floor.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/floor.json)).

## Examples

### Example 1
Calling `floor` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 2
Calling `floor` with these arguments returns `3`.
#### json
```json
{
  "x": 3.5
}
```


### Example 3
Calling `floor` with these arguments returns `-1`.
#### json
```json
{
  "x": -0.4
}
```


### Example 4
Calling `floor` with these arguments returns `-4`.
#### json
```json
{
  "x": -3.5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Round fractions down
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/floor/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/floor/schema.yaml)

## Sources

* [OpenEO Processes — floor](https://processes.openeo.org/#floor)
* [Open-EO/openeo-processes — floor.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/floor.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/rounding/floor`

