
# OpenEO type: Band Name (Schema)

`ogc.openeo.types.band-name` *v0.1*

A band name or common band name identifying a band in a data cube.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `band-name`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Either a unique band name (metadata field `name`) or a [common band name](https://github.com/radiantearth/stac-spec/tree/v0.9.0/extensions/eo#common-band-names) (metadata field `common_name`) available in the data cube. If the unique band name and the common name conflict, the unique band name has a higher priority.

## Examples

### Example value
A common Sentinel-2 band name.
#### json
```json
"B04"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: band-name
title: Band Name
description: Either a unique band name (metadata field `name`) or a [common band name](https://github.com/radiantearth/stac-spec/tree/v0.9.0/extensions/eo#common-band-names)
  (metadata field `common_name`) available in the data cube. If the unique band name
  and the common name conflict, the unique band name has a higher priority.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/band-name`

