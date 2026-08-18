
# Add dimension (Schema)

`ogc.openeo.processes.cubes.add_dimension` *v0.1*

Add a new dimension

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`add_dimension`](https://processes.openeo.org/#add_dimension) — *Add a new dimension*. It models the `arguments` object of a process graph node invoking `add_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Adds a new named dimension to the data cube.

Afterwards, the dimension can be referred to with the specified `name`. If a dimension with the specified name exists, the process fails with a `DimensionExists` exception. The dimension label of the dimension is set to the specified `label`.

## Exceptions

- `DimensionExists`: A dimension with the specified name already exists.

## Source

OpenEO Processes specification: [`add_dimension`](https://processes.openeo.org/#add_dimension) ([openeo-processes/add_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add_dimension.json)).

## Examples

### Example 1
Calling `add_dimension` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "name": "bands",
  "label": "NDVI",
  "type": "bands"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Add a new dimension
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  name:
    type: string
  label:
    anyOf:
    - type: number
    - type: string
  type:
    type: string
    enum:
    - bands
    - geometry
    - spatial
    - temporal
    - other
required:
- data
- name
- label

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/add_dimension/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/add_dimension/schema.yaml)

## Sources

* [OpenEO Processes — add_dimension](https://processes.openeo.org/#add_dimension)
* [Open-EO/openeo-processes — add_dimension.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add_dimension.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/add_dimension`

