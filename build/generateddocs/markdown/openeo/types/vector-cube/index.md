
# OpenEO type: Vector data cube (Schema)

`ogc.openeo.types.vector-cube` *v0.1*

A vector data cube (deprecated in favour of `datacube`).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `vector-cube`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

> **Note:** OpenEO marks this subtype as deprecated in its own specification; it is retained here for completeness while existing processes still reference it.

A vector data cube, which is a data cube with a dimension of type vector. This has been deprecated in favour of `datacube`.

## Examples

### Example value
A vector data cube reference; prefer the `datacube` subtype for new processes.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: vector-cube
title: Vector data cube
description: A vector data cube, which is a data cube with a dimension of type vector.
  This has been deprecated in favour of `datacube`.
deprecated: true

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/vector-cube/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/vector-cube/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/vector-cube`

