
# Array interpolate linear (Schema)

`ogc.openeo.processes.arrays.array_interpolate_linear` *v0.1*

One-dimensional linear interpolation for arrays

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_interpolate_linear`](https://processes.openeo.org/#array_interpolate_linear) — *One-dimensional linear interpolation for arrays*. It models the `arguments` object of a process graph node invoking `array_interpolate_linear`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Performs a linear interpolation for each of the NaN and no-data values in the array given, except for leading and trailing NaN and no-data values.

The linear interpolants are defined by the array indices or labels (x axis) and the values in the array (y axis).

## Source

OpenEO Processes specification: [`array_interpolate_linear`](https://processes.openeo.org/#array_interpolate_linear) ([openeo-processes/array_interpolate_linear.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_interpolate_linear.json)).

## Examples

### Example 1
Calling `array_interpolate_linear` with these arguments returns `[null, 1, 3.5, 6, -1, -8]`.
#### json
```json
{
  "data": [
    null,
    1,
    null,
    6,
    null,
    -8
  ]
}
```


### Example 2
Calling `array_interpolate_linear` with these arguments returns `[null, 1, null, null]`.
#### json
```json
{
  "data": [
    null,
    1,
    null,
    null
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: One-dimensional linear interpolation for arrays
type: object
properties:
  data:
    type: array
    items:
      type:
      - number
      - 'null'
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_interpolate_linear/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_interpolate_linear/schema.yaml)

## Sources

* [OpenEO Processes — array_interpolate_linear](https://processes.openeo.org/#array_interpolate_linear)
* [Open-EO/openeo-processes — array_interpolate_linear.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_interpolate_linear.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_interpolate_linear`

