
# Ln (Schema)

`ogc.openeo.processes.math.exponential-and-logarithmic.ln` *v0.1*

Natural logarithm

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`ln`](https://processes.openeo.org/#ln) — *Natural logarithm*. It models the `arguments` object of a process graph node invoking `ln`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The natural logarithm is the logarithm to the base *e* of the number `x`, which equals to using the *log* process with the base set to *e*. The natural logarithm is the inverse function of taking *e* to the power x.

No-data values are passed through.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, *`ln(0)`* results in -infinity if the processing environment supports it or otherwise an exception is thrown. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`ln`](https://processes.openeo.org/#ln) ([openeo-processes/ln.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ln.json)).

## Examples

### Example 1
Calling `ln` with these arguments returns `0`.
#### json
```json
{
  "x": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Natural logarithm
type: object
properties:
  x:
    type:
    - number
    - 'null'
    minimum: 0
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/ln/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/exponential-and-logarithmic/ln/schema.yaml)

## Sources

* [OpenEO Processes — ln](https://processes.openeo.org/#ln)
* [Open-EO/openeo-processes — ln.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ln.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/exponential-and-logarithmic/ln`

