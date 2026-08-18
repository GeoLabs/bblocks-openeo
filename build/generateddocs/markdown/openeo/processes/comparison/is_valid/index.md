
# Is valid (Schema)

`ogc.openeo.processes.comparison.is_valid` *v0.1*

Value is valid data

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`is_valid`](https://processes.openeo.org/#is_valid) — *Value is valid data*. It models the `arguments` object of a process graph node invoking `is_valid`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified value `x` is valid. The following values are considered valid:

* Any finite numerical value (integers and floating-point numbers). The definition of finite numbers follows the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935) and excludes the special value `NaN` (not a number).
* Any other value that is not a no-data value according to `is_nodata()`. Thus all arrays, objects and strings are valid, regardless of their content.

## Source

OpenEO Processes specification: [`is_valid`](https://processes.openeo.org/#is_valid) ([openeo-processes/is_valid.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_valid.json)).

## Examples

### Example 1
Calling `is_valid` with these arguments returns `true`.
#### json
```json
{
  "x": 1
}
```


### Example 2
Calling `is_valid` with these arguments returns `true`.
#### json
```json
{
  "x": "Test"
}
```


### Example 3
Calling `is_valid` with these arguments returns `false`.
#### json
```json
{
  "x": null
}
```


### Example 4
Calling `is_valid` with these arguments returns `true`.
#### json
```json
{
  "x": [
    null,
    null
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Value is valid data
type: object
properties:
  x:
    description: Any data type is allowed.
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_valid/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_valid/schema.yaml)

## Sources

* [OpenEO Processes — is_valid](https://processes.openeo.org/#is_valid)
* [Open-EO/openeo-processes — is_valid.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_valid.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/is_valid`

