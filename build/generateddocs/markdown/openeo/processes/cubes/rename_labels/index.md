
# Rename labels (Schema)

`ogc.openeo.processes.cubes.rename_labels` *v0.1*

Rename dimension labels

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`rename_labels`](https://processes.openeo.org/#rename_labels) — *Rename dimension labels*. It models the `arguments` object of a process graph node invoking `rename_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Renames the labels of the specified dimension in the data cube from `source` to `target`.

If the array for the source labels is empty (the default), the dimension labels are enumerated with zero-based numbering (0,1,2,3,...) so that the dimension labels directly map to the indices of the array specified for the parameter `target`. Otherwise, the number of the source and target labels must be equal. If none of these requirements is fulfilled, the `LabelMismatch` exception is thrown.

This process doesn't change the order of the labels and their corresponding data.

## Exceptions

- `LabelsNotEnumerated`: The dimension labels are not enumerated.
- `LabelMismatch`: The number of labels in the parameters `source` and `target` don't match.
- `LabelNotAvailable`: A label with the specified name does not exist.
- `LabelExists`: A label with the specified name exists.

## Source

OpenEO Processes specification: [`rename_labels`](https://processes.openeo.org/#rename_labels) ([openeo-processes/rename_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_labels.json)).

## Examples

### Rename named labels
Renaming the bands from `B1` to `red`, from `B2` to `green` and from `B3` to `blue`.

Example arguments for calling `rename_labels`.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "dimension": "bands",
  "source": [
    "B1",
    "B2",
    "B3"
  ],
  "target": [
    "red",
    "green",
    "blue"
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Rename dimension labels
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  dimension:
    type: string
  target:
    type: array
    uniqueItems: true
    items:
      type:
      - number
      - string
  source:
    type: array
    uniqueItems: true
    items:
      type:
      - number
      - string
required:
- data
- dimension
- target

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/rename_labels/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/rename_labels/schema.yaml)

## Sources

* [OpenEO Processes — rename_labels](https://processes.openeo.org/#rename_labels)
* [Open-EO/openeo-processes — rename_labels.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_labels.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/rename_labels`

