
# Linear scale range (Schema)

`ogc.openeo.processes.math.linear_scale_range` *v0.1*

Linear transformation between two ranges

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`linear_scale_range`](https://processes.openeo.org/#linear_scale_range) — *Linear transformation between two ranges*. It models the `arguments` object of a process graph node invoking `linear_scale_range`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Performs a linear transformation between the input and output range.

The given number in `x` is clipped to the bounds specified in `inputMin` and `inputMax` so that the underlying formula *`((x - inputMin) / (inputMax - inputMin)) * (outputMax - outputMin) + outputMin`* never returns a value outside of the range defined by `outputMin` and `outputMax`.

Potential use case include

* scaling values to the 8-bit range (0 - 255) often used for numeric representation of values in one of the channels of the [RGB colour model](https://en.wikipedia.org/wiki/RGB_color_model#Numeric_representations) or
* calculating percentages (0 - 100).

No-data values are passed through.

## Source

OpenEO Processes specification: [`linear_scale_range`](https://processes.openeo.org/#linear_scale_range) ([openeo-processes/linear_scale_range.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/linear_scale_range.json)).

## Examples

### Example 1
Calling `linear_scale_range` with these arguments returns `165.75`.
#### json
```json
{
  "x": 0.3,
  "inputMin": -1,
  "inputMax": 1,
  "outputMin": 0,
  "outputMax": 255
}
```


### Example 2
Calling `linear_scale_range` with these arguments returns `0.1`.
#### json
```json
{
  "x": 25.5,
  "inputMin": 0,
  "inputMax": 255
}
```


### Example 3
Calling `linear_scale_range` with these arguments returns `null`.
#### json
```json
{
  "x": null,
  "inputMin": 0,
  "inputMax": 100
}
```


### Example 4
Shows that the input data is clipped.

Calling `linear_scale_range` with these arguments returns `255`.
#### json
```json
{
  "x": 1.12,
  "inputMin": 0,
  "inputMax": 1,
  "outputMin": 0,
  "outputMax": 255
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Linear transformation between two ranges
type: object
properties:
  x:
    type:
    - number
    - 'null'
  inputMin:
    type: number
  inputMax:
    type: number
  outputMin:
    type: number
  outputMax:
    type: number
required:
- x
- inputMin
- inputMax

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/linear_scale_range/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/linear_scale_range/schema.yaml)

## Sources

* [OpenEO Processes — linear_scale_range](https://processes.openeo.org/#linear_scale_range)
* [Open-EO/openeo-processes — linear_scale_range.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/linear_scale_range.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/linear_scale_range`

