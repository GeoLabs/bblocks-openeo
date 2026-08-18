
# Mod (Schema)

`ogc.openeo.processes.math.mod` *v0.1*

Modulo

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`mod`](https://processes.openeo.org/#mod) — *Modulo*. It models the `arguments` object of a process graph node invoking `mod`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Remainder after a division of `x` by `y` for both integers and floating-point numbers.

The result of a modulo operation has the sign of the divisor. The handling regarding the sign of the result [differs between programming languages](https://en.wikipedia.org/wiki/Modulo_operation#In_programming_languages) and needs careful consideration to avoid unexpected results.

If any argument is a no-data value, the result will be the no-data value (or `null`). If `y` is set to 0 this results in:

- +infinity for `x` > 0,
- -infinity for `x` < 0,
- `NaN` for `x` = 0,
- or otherwise, throws a `DivisionByZero` exception if the other options are not supported by the processing environment.

## Exceptions

- `DivisionByZero`: Division by zero is not supported.

## Source

OpenEO Processes specification: [`mod`](https://processes.openeo.org/#mod) ([openeo-processes/mod.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mod.json)).

## Examples

### Example 1
Calling `mod` with these arguments returns `2`.
#### json
```json
{
  "x": 27,
  "y": 5
}
```


### Example 2
Calling `mod` with these arguments returns `3`.
#### json
```json
{
  "x": -27,
  "y": 5
}
```


### Example 3
Calling `mod` with these arguments returns `-0.86`.
#### json
```json
{
  "x": 3.14,
  "y": -2
}
```


### Example 4
Calling `mod` with these arguments returns `-2`.
#### json
```json
{
  "x": -27,
  "y": -5
}
```


### Example 5
Calling `mod` with these arguments returns `null`.
#### json
```json
{
  "x": 27,
  "y": null
}
```


### Example 6
Calling `mod` with these arguments returns `null`.
#### json
```json
{
  "x": null,
  "y": 5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Modulo
type: object
properties:
  x:
    type:
    - number
    - 'null'
  y:
    type:
    - number
    - 'null'
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/mod/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/mod/schema.yaml)

## Sources

* [OpenEO Processes — mod](https://processes.openeo.org/#mod)
* [Open-EO/openeo-processes — mod.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mod.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/mod`

