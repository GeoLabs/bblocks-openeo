
# Log (Schema)

`ogc.openeo.processes.math.exponential-and-logarithmic.log` *v0.1*

Logarithm to a base

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`log`](https://processes.openeo.org/#log) — *Logarithm to a base*. It models the `arguments` object of a process graph node invoking `log`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Logarithm to the base `base` of the number `x` is defined to be the inverse function of taking b to the power of x.

If any argument is a no-data value, the result will be the no-data value (or `null`).

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, having `x` set to `0` with any base results in -infinity if the processing environment supports it or otherwise an exception is thrown. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`log`](https://processes.openeo.org/#log) ([openeo-processes/log.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/log.json)).

## Examples

### Example 1
Calling `log` with these arguments returns `1`.
#### json
```json
{
  "x": 10,
  "base": 10
}
```


### Example 2
Calling `log` with these arguments returns `1`.
#### json
```json
{
  "x": 2,
  "base": 2
}
```


### Example 3
Calling `log` with these arguments returns `2`.
#### json
```json
{
  "x": 4,
  "base": 2
}
```


### Example 4
Calling `log` with these arguments returns `0`.
#### json
```json
{
  "x": 1,
  "base": 16
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Logarithm to a base
type: object
properties:
  x:
    type:
    - number
    - 'null'
    minimum: 0
  base:
    type:
    - number
    - 'null'
required:
- x
- base

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/log/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/log/schema.yaml)

## Sources

* [OpenEO Processes — log](https://processes.openeo.org/#log)
* [Open-EO/openeo-processes — log.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/log.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/exponential-and-logarithmic/log`

