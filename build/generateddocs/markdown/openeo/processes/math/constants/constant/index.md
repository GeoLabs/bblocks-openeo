
# Constant (Schema)

`ogc.openeo.processes.math.constants.constant` *v0.1*

Define a constant value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`constant`](https://processes.openeo.org/#constant) — *Define a constant value*. It models the `arguments` object of a process graph node invoking `constant`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Defines a constant value that can be reused in multiple places of a process.

## Source

OpenEO Processes specification: [`constant`](https://processes.openeo.org/#constant) ([openeo-processes/constant.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/constant.json)).

## Examples

### A constant string value
Calling `constant` with these arguments returns `42`.
#### json
```json
{
  "x": 42
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Define a constant value
type: object
properties:
  x:
    description: Any data type.
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/constant/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/constant/schema.yaml)

## Sources

* [OpenEO Processes — constant](https://processes.openeo.org/#constant)
* [Open-EO/openeo-processes — constant.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/constant.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/constants/constant`

