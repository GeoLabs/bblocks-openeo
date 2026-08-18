
# Filter labels (Schema)

`ogc.openeo.processes.cubes.filter_labels` *v0.1*

Filter dimension labels based on a condition

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`filter_labels`](https://processes.openeo.org/#filter_labels) — *Filter dimension labels based on a condition*. It models the `arguments` object of a process graph node invoking `filter_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the dimension labels in the data cube for the given dimension. Only the dimension labels that match the specified condition are preserved, all other labels with their corresponding data get removed.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `value`: A single dimension label to compare against. The data type of the parameter depends on the dimension labels set for the dimension. Please note that for some dimension types a representation is used, e.g.

* dates and/or times are usually strings compliant to [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601),
* geometries can be a WKT string or an identifier.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the dimension label should be kept in the data cube, otherwise `false`.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`filter_labels`](https://processes.openeo.org/#filter_labels) ([openeo-processes/filter_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_labels.json)).

## Examples

### Example 1
Filters the data cube to only contain data from platform Sentinel-2A. This example assumes that the data cube has a dimension `platform` so that computations can distinguish between Sentinel-2A and Sentinel-2B data.

Example arguments for calling `filter_labels`.
#### json
```json
{
  "data": {
    "from_parameter": "sentinel2_data"
  },
  "condition": {
    "process_graph": {
      "eq": {
        "process_id": "eq",
        "arguments": {
          "x": {
            "from_parameter": "value"
          },
          "y": "Sentinel-2A",
          "case_sensitive": false
        },
        "result": true
      }
    }
  },
  "dimension": "platform"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Filter dimension labels based on a condition
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  condition:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  dimension:
    type: string
  context:
    description: Any data type.
required:
- data
- condition
- dimension

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_labels/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_labels/schema.yaml)

## Sources

* [OpenEO Processes — filter_labels](https://processes.openeo.org/#filter_labels)
* [Open-EO/openeo-processes — filter_labels.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_labels.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/filter_labels`

