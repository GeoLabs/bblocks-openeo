
# Is nan (Schema)

`ogc.openeo.processes.comparison.is_nan` *v0.1*

Value is not a number

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`is_nan`](https://processes.openeo.org/#is_nan) — *Value is not a number*. It models the `arguments` object of a process graph node invoking `is_nan`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified value `x` carries the special value `NaN` (not a number) as defined by the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935), in which case it returns `true`. Returns `false` otherwise.

## Source

OpenEO Processes specification: [`is_nan`](https://processes.openeo.org/#is_nan) ([openeo-processes/is_nan.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nan.json)).

## Examples

### An ordinary number is not NaN
Calling `is_nan` with these arguments returns `false`.

JSON has no literal representation for `NaN`, so a JSON example cannot demonstrate the `true` branch; in a process graph, a NaN value typically arises from a prior computation (e.g. `0 / 0`) rather than from a literal argument.
#### json
```json
{
  "x": 5
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Value is not a number
type: object
properties:
  x:
    description: Any data type is allowed.
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_nan/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_nan/schema.yaml)

## Sources

* [OpenEO Processes — is_nan](https://processes.openeo.org/#is_nan)
* [Open-EO/openeo-processes — is_nan.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nan.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/is_nan`

