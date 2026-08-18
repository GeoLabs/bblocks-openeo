
# Add (Schema)

`ogc.openeo.processes.math.add` *v0.1*

Addition of two numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`add`](https://processes.openeo.org/#add) — *Addition of two numbers*. It models the `arguments` object of a process graph node invoking `add`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Sums up the two numbers `x` and `y` (*`x + y`*) and returns the computed sum.

No-data values are taken into account so that the no-data value is returned if any element is such a value.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

## Source

OpenEO Processes specification: [`add`](https://processes.openeo.org/#add) ([openeo-processes/add.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add.json)).

## Examples

### Example 1
Calling `add` with these arguments returns `7.5`.
#### json
```json
{
  "x": 5,
  "y": 2.5
}
```


### Example 2
Calling `add` with these arguments returns `-6`.
#### json
```json
{
  "x": -2,
  "y": -4
}
```


### Example 3
Calling `add` with these arguments returns `null`.
#### json
```json
{
  "x": 1,
  "y": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Addition of two numbers
type: object
properties:
  x:
    type:
    - number
    - 'null'
  y:
    type:
    - number
    - 'null'
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/add/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/add/schema.yaml)

## Sources

* [OpenEO Processes — add](https://processes.openeo.org/#add)
* [Open-EO/openeo-processes — add.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/add.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/add`

