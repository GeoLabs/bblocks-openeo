
# OpenEO type: Date only (Schema)

`ogc.openeo.types.date` *v0.1*

A calendar date without a time component (RFC 3339 full-date, UTC).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `date`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Date only representation, as defined for `full-date` by [RFC 3339 in section 5.6](https://www.rfc-editor.org/rfc/rfc3339.html#section-5.6). The time zone is UTC. Missing time components are all 0.

## Examples

### Example value
A date without time or time zone information.
#### json
```json
"2026-08-03"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: date
format: date
title: Date only
description: Date only representation, as defined for `full-date` by [RFC 3339 in
  section 5.6](https://www.rfc-editor.org/rfc/rfc3339.html#section-5.6). The time
  zone is UTC. Missing time components are all 0.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/date`

