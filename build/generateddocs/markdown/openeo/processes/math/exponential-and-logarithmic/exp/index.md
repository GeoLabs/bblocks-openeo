
# Exp (Schema)

`ogc.openeo.processes.math.exponential-and-logarithmic.exp` *v0.1*

Exponentiation to the base e

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`exp`](https://processes.openeo.org/#exp) — *Exponentiation to the base e*. It models the `arguments` object of a process graph node invoking `exp`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Exponential function to the base *e* raised to the power of `p`.

No-data values are passed through.

## Source

OpenEO Processes specification: [`exp`](https://processes.openeo.org/#exp) ([openeo-processes/exp.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/exp.json)).

## Examples

### Example 1
Calling `exp` with these arguments returns `1`.
#### json
```json
{
  "p": 0
}
```


### Example 2
Calling `exp` with these arguments returns `null`.
#### json
```json
{
  "p": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Exponentiation to the base e
type: object
properties:
  p:
    type:
    - number
    - 'null'
required:
- p

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/exp/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/exp/schema.yaml)

## Sources

* [OpenEO Processes — exp](https://processes.openeo.org/#exp)
* [Open-EO/openeo-processes — exp.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/exp.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/exponential-and-logarithmic/exp`

