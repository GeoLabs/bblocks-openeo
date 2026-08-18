
# OpenEO type: Collection ID (Schema)

`ogc.openeo.types.collection-id` *v0.1*

An identifier for a collection offered by an OpenEO back-end.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `collection-id`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A collection identifier from the list of supported collections.

## Examples

### Example value
A collection identifier for Sentinel-2 Level-2A data.
#### json
```json
"SENTINEL2_L2A"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: collection-id
title: Collection ID
description: A collection identifier from the list of supported collections.
pattern: ^[\w\-\.~/]+$

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/collection-id/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/collection-id/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/collection-id`

