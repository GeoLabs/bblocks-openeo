
# Round (Schema)

`ogc.openeo.processes.math.rounding.round` *v0.1*

Round to a specified precision

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`round`](https://processes.openeo.org/#round) — *Round to a specified precision*. It models the `arguments` object of a process graph node invoking `round`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Rounds a real number `x` to specified precision `p`.

If `x` is halfway between closest numbers of precision `p`, it is rounded to the closest even number of precision `p`.
This behavior follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) and is often called "round to nearest (even)" or "banker's rounding". It minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.

No-data values are passed through.

## Source

OpenEO Processes specification: [`round`](https://processes.openeo.org/#round) ([openeo-processes/round.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/round.json)).

## Examples

### Example 1
Calling `round` with these arguments returns `0`.
#### json
```json
{
  "x": 0
}
```


### Example 2
Calling `round` with these arguments returns `3.6`.
#### json
```json
{
  "x": 3.56,
  "p": 1
}
```


### Example 3
Calling `round` with these arguments returns `-0.44`.
#### json
```json
{
  "x": -0.4444444,
  "p": 2
}
```


### Example 4
Calling `round` with these arguments returns `-2`.
#### json
```json
{
  "x": -2.5
}
```


### Example 5
Calling `round` with these arguments returns `-4`.
#### json
```json
{
  "x": -3.5
}
```


### Example 6
Calling `round` with these arguments returns `0.2`.
#### json
```json
{
  "x": 0.25,
  "p": 1
}
```


### Example 7
Calling `round` with these arguments returns `0.4`.
#### json
```json
{
  "x": 0.35,
  "p": 1
}
```


### Example 8
Calling `round` with these arguments returns `1200`.
#### json
```json
{
  "x": 1234.5,
  "p": -2
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Round to a specified precision
type: object
properties:
  x:
    type:
    - number
    - 'null'
  p:
    type: integer
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/round/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/rounding/round/schema.yaml)

## Sources

* [OpenEO Processes — round](https://processes.openeo.org/#round)
* [Open-EO/openeo-processes — round.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/round.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/rounding/round`

