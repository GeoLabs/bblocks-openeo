
# Multiply (Schema)

`ogc.openeo.processes.math.multiply` *v0.1*

Multiplication of two numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`multiply`](https://processes.openeo.org/#multiply) — *Multiplication of two numbers*. It models the `arguments` object of a process graph node invoking `multiply`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Multiplies the two numbers `x` and `y` (*`x * y`*) and returns the computed product.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

## Exceptions

- `MultiplicandMissing`: Multiplication requires at least two numbers.

## Source

OpenEO Processes specification: [`multiply`](https://processes.openeo.org/#multiply) ([openeo-processes/multiply.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/multiply.json)).

## Examples

### Example 1
Calling `multiply` with these arguments returns `12.5`.
#### json
```json
{
  "x": 5,
  "y": 2.5
}
```


### Example 2
Calling `multiply` with these arguments returns `8`.
#### json
```json
{
  "x": -2,
  "y": -4
}
```


### Example 3
Calling `multiply` with these arguments returns `null`.
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
description: Multiplication of two numbers
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/multiply/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/multiply/schema.yaml)

## Sources

* [OpenEO Processes — multiply](https://processes.openeo.org/#multiply)
* [Open-EO/openeo-processes — multiply.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/multiply.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/multiply`

