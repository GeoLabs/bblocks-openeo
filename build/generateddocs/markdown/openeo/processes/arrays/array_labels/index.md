
# Array labels (Schema)

`ogc.openeo.processes.arrays.array_labels` *v0.1*

Get the labels for an array

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_labels`](https://processes.openeo.org/#array_labels) — *Get the labels for an array*. It models the `arguments` object of a process graph node invoking `array_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives all labels for a labeled array or gives all indices for an array without labels. If the array is not labeled, an array with the zero-based indices is returned. The labels or indices have the same order as in the array.

## Source

OpenEO Processes specification: [`array_labels`](https://processes.openeo.org/#array_labels) ([openeo-processes/array_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_labels.json)).

## Examples

### Labels of an unlabeled array
For an array without labels, the zero-based indices are returned.

Calling `array_labels` with these arguments returns `[0, 1, 2]`.
#### json
```json
{
  "data": [
    "a",
    "b",
    "c"
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Get the labels for an array
type: object
properties:
  data:
    type: array
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_labels/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_labels/schema.yaml)

## Sources

* [OpenEO Processes — array_labels](https://processes.openeo.org/#array_labels)
* [Open-EO/openeo-processes — array_labels.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_labels.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_labels`

