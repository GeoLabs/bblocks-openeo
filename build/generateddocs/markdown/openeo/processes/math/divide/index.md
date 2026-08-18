
# Divide (Schema)

`ogc.openeo.processes.math.divide` *v0.1*

Division of two numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`divide`](https://processes.openeo.org/#divide) — *Division of two numbers*. It models the `arguments` object of a process graph node invoking `divide`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Divides argument `x` by the argument `y` (*`x / y`*) and returns the computed result.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. A division by zero results in:

- +infinity for `x` > 0,
- -infinity for `x` < 0,
- `NaN` for `x` = 0,
- or otherwise, throws a `DivisionByZero` exception if the other options are not supported by the processing environment.

## Exceptions

- `DivisionByZero`: Division by zero is not supported.

## Source

OpenEO Processes specification: [`divide`](https://processes.openeo.org/#divide) ([openeo-processes/divide.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/divide.json)).

## Examples

### Example 1
Calling `divide` with these arguments returns `2`.
#### json
```json
{
  "x": 5,
  "y": 2.5
}
```


### Example 2
Calling `divide` with these arguments returns `-0.5`.
#### json
```json
{
  "x": -2,
  "y": 4
}
```


### Example 3
Calling `divide` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Division of two numbers
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/divide/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/divide/schema.yaml)

## Sources

* [OpenEO Processes — divide](https://processes.openeo.org/#divide)
* [Open-EO/openeo-processes — divide.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/divide.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/divide`

