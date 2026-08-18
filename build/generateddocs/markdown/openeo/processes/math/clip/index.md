
# Clip (Schema)

`ogc.openeo.processes.math.clip` *v0.1*

Clip a value between a minimum and a maximum

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`clip`](https://processes.openeo.org/#clip) — *Clip a value between a minimum and a maximum*. It models the `arguments` object of a process graph node invoking `clip`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Clips a number between specified minimum and maximum values. A value larger than the maximum value is set to the maximum value, a value lower than the minimum value is set to the minimum value. If the maximum value is smaller than the minimum number, the process throws a `MinMaxSwapped` exception.

No-data values are passed through.

## Exceptions

- `MinMaxSwapped`: The minimum value should be lower than or equal to the maximum value.

## Source

OpenEO Processes specification: [`clip`](https://processes.openeo.org/#clip) ([openeo-processes/clip.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/clip.json)).

## Examples

### Example 1
Calling `clip` with these arguments returns `-1`.
#### json
```json
{
  "x": -5,
  "min": -1,
  "max": 1
}
```


### Example 2
Calling `clip` with these arguments returns `10`.
#### json
```json
{
  "x": 10.001,
  "min": 1,
  "max": 10
}
```


### Example 3
Calling `clip` with these arguments returns `1e-06`.
#### json
```json
{
  "x": 1e-06,
  "min": 0,
  "max": 0.02
}
```


### Example 4
Calling `clip` with these arguments returns `null`.
#### json
```json
{
  "x": null,
  "min": 0,
  "max": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Clip a value between a minimum and a maximum
type: object
properties:
  x:
    type:
    - number
    - 'null'
  min:
    type: number
  max:
    type: number
required:
- x
- min
- max

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/clip/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/clip/schema.yaml)

## Sources

* [OpenEO Processes — clip](https://processes.openeo.org/#clip)
* [Open-EO/openeo-processes — clip.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/clip.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/clip`

