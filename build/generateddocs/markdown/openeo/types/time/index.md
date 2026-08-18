
# OpenEO type: Time only (Schema)

`ogc.openeo.types.time` *v0.1*

A time of day without a date component (UTC).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `time`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Time only representation, as defined for `partial-time` by [RFC 3339 in section 5.6](https://www.rfc-editor.org/rfc/rfc3339.html#section-5.6). The time zone is UTC.

## Examples

### Example value
Noon, UTC.
#### json
```json
"12:00:00"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: time
pattern: ^\d{2}:\d{2}:\d{2}$
title: Time only
description: Time only representation, as defined for `partial-time` by [RFC 3339
  in section 5.6](https://www.rfc-editor.org/rfc/rfc3339.html#section-5.6). The time
  zone is UTC.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/time`

