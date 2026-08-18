
# OpenEO type: Raster data cube (Schema)

`ogc.openeo.types.raster-cube` *v0.1*

A raster data cube (deprecated in favour of `datacube`).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `raster-cube`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

> **Note:** OpenEO marks this subtype as deprecated in its own specification; it is retained here for completeness while existing processes still reference it.

A raster data cube, which is a data cube with two dimension of type spatial (x and y). This has been deprecated in favour of `datacube`.

## Examples

### Example value
A raster data cube reference; prefer the `datacube` subtype for new processes.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: raster-cube
title: Raster data cube
description: A raster data cube, which is a data cube with two dimension of type spatial
  (x and y). This has been deprecated in favour of `datacube`.
deprecated: true

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/raster-cube/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/raster-cube/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/raster-cube`

