
# Drop dimension (Schema)

`ogc.openeo.processes.cubes.drop_dimension` *v0.1*

Remove a dimension

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`drop_dimension`](https://processes.openeo.org/#drop_dimension) — *Remove a dimension*. It models the `arguments` object of a process graph node invoking `drop_dimension`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Drops a dimension from the data cube.

Dropping a dimension only works on dimensions with a single dimension label left, otherwise the process fails with a `DimensionLabelCountMismatch` exception. Dimension values can be reduced to a single value with a filter such as `filter_bands()` or the `reduce_dimension()` process. If a dimension with the specified name does not exist, the process fails with a `DimensionNotAvailable` exception.

## Exceptions

- `DimensionLabelCountMismatch`: The number of dimension labels exceeds one, which requires a reducer.
- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`drop_dimension`](https://processes.openeo.org/#drop_dimension) ([openeo-processes/drop_dimension.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/drop_dimension.json)).

## Examples

### Example 1
Calling `drop_dimension` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "name": "bands"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Remove a dimension
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  name:
    type: string
required:
- data
- name

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/drop_dimension/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/drop_dimension/schema.yaml)

## Sources

* [OpenEO Processes — drop_dimension](https://processes.openeo.org/#drop_dimension)
* [Open-EO/openeo-processes — drop_dimension.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/drop_dimension.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/drop_dimension`

