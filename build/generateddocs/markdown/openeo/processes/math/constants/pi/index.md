
# Pi (Schema)

`ogc.openeo.processes.math.constants.pi` *v0.1*

Pi (π)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`pi`](https://processes.openeo.org/#pi) — *Pi (π)*. It models the `arguments` object of a process graph node invoking `pi`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The real number Pi (π) is a mathematical constant that is the ratio of the circumference of a circle to its diameter. The numerical value is approximately *3.14159*.

## Source

OpenEO Processes specification: [`pi`](https://processes.openeo.org/#pi) ([openeo-processes/pi.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/pi.json)).

## Examples

### Pi
Calling `pi` with these arguments returns `3.141592653589793`.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: "Pi (\u03C0)"
type: object
properties: {}

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/pi/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/constants/pi/schema.yaml)

## Sources

* [OpenEO Processes — pi](https://processes.openeo.org/#pi)
* [Open-EO/openeo-processes — pi.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/pi.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/constants/pi`

