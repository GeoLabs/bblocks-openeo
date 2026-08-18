
# OpenEO type: GeoJSON (Schema)

`ogc.openeo.types.geojson` *v0.1*

A GeoJSON geometry, feature or feature collection (deprecated in favour of `datacube`/`vector-cube` handling).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `geojson`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

> **Note:** OpenEO marks this subtype as deprecated in its own specification; it is retained here for completeness while existing processes still reference it.

GeoJSON as defined by [RFC 7946](https://www.rfc-editor.org/rfc/rfc7946.html). The GeoJSON type `GeometryCollection` is not supported.

## Examples

### Example value
A GeoJSON point geometry.
#### json
```json
{
  "type": "Point",
  "coordinates": [
    16.37,
    48.21
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: geojson
title: GeoJSON
description: GeoJSON as defined by [RFC 7946](https://www.rfc-editor.org/rfc/rfc7946.html).
  The GeoJSON type `GeometryCollection` is not supported.
deprecated: true
allOf:
- $ref: https://geojson.org/schema/GeoJSON.json

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/geojson`

