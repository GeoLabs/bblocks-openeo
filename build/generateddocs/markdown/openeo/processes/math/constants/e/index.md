
# E (Schema)

`ogc.openeo.processes.math.constants.e` *v0.1*

Euler's number (e)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`e`](https://processes.openeo.org/#e) — *Euler's number (e)*. It models the `arguments` object of a process graph node invoking `e`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The real number *e* is a mathematical constant that is the base of the natural logarithm such that *`ln(e) = 1`*. The numerical value is approximately *2.71828*.

## Source

OpenEO Processes specification: [`e`](https://processes.openeo.org/#e) ([openeo-processes/e.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/e.json)).

## Examples

### Euler's number
Calling `e` with these arguments returns `2.718281828459045`.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Euler's number (e)
type: object
properties: {}

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/e/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/e/schema.yaml)

## Sources

* [OpenEO Processes — e](https://processes.openeo.org/#e)
* [Open-EO/openeo-processes — e.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/e.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/constants/e`

