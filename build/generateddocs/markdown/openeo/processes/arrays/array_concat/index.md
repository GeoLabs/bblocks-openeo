
# Array concat (Schema)

`ogc.openeo.processes.arrays.array_concat` *v0.1*

Merge two arrays

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_concat`](https://processes.openeo.org/#array_concat) — *Merge two arrays*. It models the `arguments` object of a process graph node invoking `array_concat`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Concatenates two arrays into a single array by appending the second array to the first array.

Array labels are kept only if both given arrays are labeled. Otherwise, the labels get discarded from both arrays. The process fails with an `ArrayLabelConflict` exception if a label is present in both arrays. Conflicts must be resolved beforehand.

## Exceptions

- `ArrayLabelConflict`: At least one label exists in both arrays and the conflict must be resolved before.

## Source

OpenEO Processes specification: [`array_concat`](https://processes.openeo.org/#array_concat) ([openeo-processes/array_concat.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_concat.json)).

## Examples

### Example 1
Concatenates two numerical arrays.

Calling `array_concat` with these arguments returns `[1.5, 2.5, 5]`.
#### json
```json
{
  "array1": [
    1.5,
    2.5
  ],
  "array2": [
    5
  ]
}
```


### Example 2
Concatenates two arrays containing different data type, may not always be supported.

Calling `array_concat` with these arguments returns `["a", "b", 1, 2]`.
#### json
```json
{
  "array1": [
    "a",
    "b"
  ],
  "array2": [
    1,
    2
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Merge two arrays
type: object
properties:
  array1:
    type: array
    items:
      description: Any data type is allowed.
  array2:
    type: array
    items:
      description: Any data type is allowed.
required:
- array1
- array2

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_concat/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_concat/schema.yaml)

## Sources

* [OpenEO Processes — array_concat](https://processes.openeo.org/#array_concat)
* [Open-EO/openeo-processes — array_concat.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_concat.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_concat`

