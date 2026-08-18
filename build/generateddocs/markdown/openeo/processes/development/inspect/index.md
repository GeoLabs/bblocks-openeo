
# Inspect (Schema)

`ogc.openeo.processes.development.inspect` *v0.1*

Add information to the logs

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`inspect`](https://processes.openeo.org/#inspect) — *Add information to the logs*. It models the `arguments` object of a process graph node invoking `inspect`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

This process can be used to add runtime information to the logs, e.g. for debugging purposes. This process should be used with caution and it is recommended to remove the process in production workflows. For example, logging each value or array individually in a process such as `apply()` or `reduce_dimension()` could lead to a (too) large number of log entries. Several data structures (e.g. data cubes) are too large to log and will only return summaries of their contents.

The data provided in the parameter `data` is returned without changes.

## Source

OpenEO Processes specification: [`inspect`](https://processes.openeo.org/#inspect) ([openeo-processes/inspect.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/inspect.json)).

## Examples

### Log a value for debugging
Calling `inspect` with these arguments returns `42`.
#### json
```json
{
  "data": 42,
  "message": "checking value",
  "level": "debug"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Add information to the logs
type: object
properties:
  data:
    description: Any data type is allowed.
  message:
    type: string
  code:
    type: string
  level:
    type: string
    enum:
    - error
    - warning
    - info
    - debug
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/development/inspect/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/development/inspect/schema.yaml)

## Sources

* [OpenEO Processes — inspect](https://processes.openeo.org/#inspect)
* [Open-EO/openeo-processes — inspect.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/inspect.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/development/inspect`

