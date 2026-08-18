
# OpenEO type: STAC resource (Schema)

`ogc.openeo.types.stac` *v0.1*

A STAC Catalog, Collection, or Item.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `stac`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A STAC Catalog, Collection, or Item, as defined by the [STAC specification](https://stacspec.org) version 0.9.0 or later.

## Examples

### Example value
A minimal valid STAC Item (no geometry).
#### json
```json
{
  "type": "Feature",
  "stac_version": "1.0.0",
  "id": "sample-item",
  "geometry": null,
  "properties": {
    "datetime": "2020-01-01T00:00:00Z"
  },
  "links": [],
  "assets": {}
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: stac
title: STAC resource
description: A STAC Catalog, Collection, or Item, as defined by the [STAC specification](https://stacspec.org)
  version 0.9.0 or later.
oneOf:
- $ref: http://schemas.stacspec.org/v1.0.0/catalog-spec/json-schema/catalog.json
- $ref: http://schemas.stacspec.org/v1.0.0/collection-spec/json-schema/collection.json
- $ref: http://schemas.stacspec.org/v1.0.0/item-spec/json-schema/item.json

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/stac/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/stac/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/stac`

