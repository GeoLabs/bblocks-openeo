
# Between (Schema)

`ogc.openeo.processes.comparison.between` *v0.1*

Between comparison

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`between`](https://processes.openeo.org/#between) — *Between comparison*. It models the `arguments` object of a process graph node invoking `between`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

By default, this process checks whether `x` is greater than or equal to `min` and lower than or equal to `max`, which is the same as computing `and(gte(x, min), lte(x, max))`. Therefore, all definitions from `and()`, `gte()` and `lte()` apply here as well.

If `exclude_max` is set to `true` the upper bound is excluded so that the process checks whether `x` is greater than or equal to `min` and lower than `max`. In this case, the process works the same as computing `and(gte(x, min), lt(x, max))`.

Lower and upper bounds are not allowed to be swapped. So `min` MUST be lower than or equal to `max` or otherwise the process always returns `false`.

## Source

OpenEO Processes specification: [`between`](https://processes.openeo.org/#between) ([openeo-processes/between.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/between.json)).

## Examples

### Example 1
Calling `between` with these arguments returns `null`.
#### json
```json
{
  "x": null,
  "min": 0,
  "max": 1
}
```


### Example 2
Calling `between` with these arguments returns `true`.
#### json
```json
{
  "x": 1,
  "min": 0,
  "max": 1
}
```


### Example 3
Calling `between` with these arguments returns `false`.
#### json
```json
{
  "x": 1,
  "min": 0,
  "max": 1,
  "exclude_max": true
}
```


### Example 4
Swapped bounds (min is greater than max) MUST always return `false`.

Calling `between` with these arguments returns `false`.
#### json
```json
{
  "x": 0.5,
  "min": 1,
  "max": 0
}
```


### Example 5
Calling `between` with these arguments returns `true`.
#### json
```json
{
  "x": -0.5,
  "min": -1,
  "max": 0
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Between comparison
type: object
properties:
  x:
    description: Any data type is allowed.
  min:
    type: number
  max:
    type: number
  exclude_max:
    type: boolean
required:
- x
- min
- max

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/between/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/between/schema.yaml)

## Sources

* [OpenEO Processes — between](https://processes.openeo.org/#between)
* [Open-EO/openeo-processes — between.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/between.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/between`

