
# Not (Schema)

`ogc.openeo.processes.logic.not` *v0.1*

Inverting a boolean

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`not`](https://processes.openeo.org/#not) — *Inverting a boolean*. It models the `arguments` object of a process graph node invoking `not`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Inverts a single boolean so that `true` gets `false` and `false` gets `true`.

No-data values are passed through.

## Source

OpenEO Processes specification: [`not`](https://processes.openeo.org/#not) ([openeo-processes/not.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/not.json)).

## Examples

### Example 1
Calling `not` with these arguments returns `null`.
#### json
```json
{
  "x": null
}
```


### Example 2
Calling `not` with these arguments returns `true`.
#### json
```json
{
  "x": false
}
```


### Example 3
Calling `not` with these arguments returns `false`.
#### json
```json
{
  "x": true
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Inverting a boolean
type: object
properties:
  x:
    type:
    - boolean
    - 'null'
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/not/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/not/schema.yaml)

## Sources

* [OpenEO Processes — not](https://processes.openeo.org/#not)
* [Open-EO/openeo-processes — not.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/not.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/not`

