
# Sgn (Schema)

`ogc.openeo.processes.math.sgn` *v0.1*

Signum

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`sgn`](https://processes.openeo.org/#sgn) — *Signum*. It models the `arguments` object of a process graph node invoking `sgn`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The signum (also known as *sign*) of `x` is defined as:

* *1* if *x > 0*
* *0* if *x = 0*
* *-1* if *x < 0*

No-data values are passed through.

## Source

OpenEO Processes specification: [`sgn`](https://processes.openeo.org/#sgn) ([openeo-processes/sgn.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sgn.json)).

## Examples

### Example 1
Calling `sgn` with these arguments returns `-1`.
#### json
```json
{
  "x": -2
}
```


### Example 2
Calling `sgn` with these arguments returns `1`.
#### json
```json
{
  "x": 3.5
}
```


### Example 3
Calling `sgn` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 4
Calling `sgn` with these arguments returns `null`.
#### json
```json
{
  "x": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Signum
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sgn/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/sgn/schema.yaml)

## Sources

* [OpenEO Processes — sgn](https://processes.openeo.org/#sgn)
* [Open-EO/openeo-processes — sgn.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sgn.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/sgn`

