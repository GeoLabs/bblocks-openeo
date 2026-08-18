
# Dimension labels (Schema)

`ogc.openeo.processes.cubes.dimension_labels` *v0.1*

Get the dimension labels

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`dimension_labels`](https://processes.openeo.org/#dimension_labels) — *Get the dimension labels*. It models the `arguments` object of a process graph node invoking `dimension_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives all labels for a dimension in the data cube. The labels have the same order as in the data cube.

If a dimension with the specified name does not exist, the process fails with a `DimensionNotAvailable` exception.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`dimension_labels`](https://processes.openeo.org/#dimension_labels) ([openeo-processes/dimension_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/dimension_labels.json)).

## Examples

### Example 1
Calling `dimension_labels` with these arguments returns `["B02", "B03", "B04", "B08"]`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is illustrative — actual labels depend on the input data cube's dimension metadata, which isn't known outside a real process graph.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "dimension": "bands"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Get the dimension labels
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  dimension:
    type: string
required:
- data
- dimension

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/dimension_labels/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/dimension_labels/schema.yaml)

## Sources

* [OpenEO Processes — dimension_labels](https://processes.openeo.org/#dimension_labels)
* [Open-EO/openeo-processes — dimension_labels.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/dimension_labels.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/dimension_labels`

