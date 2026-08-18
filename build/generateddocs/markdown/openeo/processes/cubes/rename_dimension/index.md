
# Rename dimension (Schema)

`ogc.openeo.processes.cubes.rename_dimension` *v0.1*

Rename a dimension

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`rename_dimension`](https://processes.openeo.org/#rename_dimension) — *Rename a dimension*. It models the `arguments` object of a process graph node invoking `rename_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Renames a dimension in the data cube while preserving all other properties.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.
- `DimensionExists`: A dimension with the specified name already exists.

## Source

OpenEO Processes specification: [`rename_dimension`](https://processes.openeo.org/#rename_dimension) ([openeo-processes/rename_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_dimension.json)).

## Examples

### Example 1
Calling `rename_dimension` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "source": "t",
  "target": "time"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Rename a dimension
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  source:
    type: string
  target:
    type: string
required:
- data
- source
- target

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/rename_dimension/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/rename_dimension/schema.yaml)

## Sources

* [OpenEO Processes — rename_dimension](https://processes.openeo.org/#rename_dimension)
* [Open-EO/openeo-processes — rename_dimension.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_dimension.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/rename_dimension`

