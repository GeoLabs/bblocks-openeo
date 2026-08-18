
# Power (Schema)

`ogc.openeo.processes.math.power` *v0.1*

Exponentiation

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`power`](https://processes.openeo.org/#power) — *Exponentiation*. It models the `arguments` object of a process graph node invoking `power`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the exponentiation for the base `base` raised to the power of `p`.

If any argument is a no-data value, the result will be the no-data value (or `null`).

## Source

OpenEO Processes specification: [`power`](https://processes.openeo.org/#power) ([openeo-processes/power.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/power.json)).

## Examples

### Example 1
Calling `power` with these arguments returns `0`.
#### json
```json
{
  "base": 0,
  "p": 2
}
```


### Example 2
Calling `power` with these arguments returns `1`.
#### json
```json
{
  "base": 2.5,
  "p": 0
}
```


### Example 3
Calling `power` with these arguments returns `27`.
#### json
```json
{
  "base": 3,
  "p": 3
}
```


### Example 4
Calling `power` with these arguments returns `0.2`.
#### json
```json
{
  "base": 5,
  "p": -1
}
```


### Example 5
Calling `power` with these arguments returns `1`.
#### json
```json
{
  "base": 1,
  "p": 0.5
}
```


### Example 6
Calling `power` with these arguments returns `null`.
#### json
```json
{
  "base": 1,
  "p": null
}
```


### Example 7
Calling `power` with these arguments returns `null`.
#### json
```json
{
  "base": null,
  "p": 2
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Exponentiation
type: object
properties:
  base:
    type:
    - number
    - 'null'
  p:
    type:
    - number
    - 'null'
required:
- base
- p

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/power/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/power/schema.yaml)

## Sources

* [OpenEO Processes — power](https://processes.openeo.org/#power)
* [Open-EO/openeo-processes — power.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/power.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/power`

