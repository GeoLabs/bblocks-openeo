
# Trim cube (Schema)

`ogc.openeo.processes.cubes.trim_cube` *v0.1*

Remove dimension labels with no-data values

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`trim_cube`](https://processes.openeo.org/#trim_cube) — *Remove dimension labels with no-data values*. It models the `arguments` object of a process graph node invoking `trim_cube`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Removes dimension labels solely containing no-data values. If the dimension is irregular categorical then dimension labels in the middle can be removed.

## Source

OpenEO Processes specification: [`trim_cube`](https://processes.openeo.org/#trim_cube) ([openeo-processes/trim_cube.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/trim_cube.json)).

## Examples

### Example 1
Calling `trim_cube` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Remove dimension labels with no-data values
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/trim_cube/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/trim_cube/schema.yaml)

## Sources

* [OpenEO Processes — trim_cube](https://processes.openeo.org/#trim_cube)
* [Open-EO/openeo-processes — trim_cube.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/trim_cube.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/trim_cube`

