
# OpenEO type: URI (Schema)

`ogc.openeo.types.uri` *v0.1*

A URI as defined by RFC 3986.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `uri`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A valid URI according to [RFC3986](https://www.rfc-editor.org/rfc/rfc3986.html). Can be restricted using a regular expression, e.g. to (dis)allow certain protocols.

## Examples

### Example value
A URI pointing to an external resource.
#### json
```json
"https://example.com/data.tif"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: uri
format: uri
title: URI
description: A valid URI according to [RFC3986](https://www.rfc-editor.org/rfc/rfc3986.html).
  Can be restricted using a regular expression, e.g. to (dis)allow certain protocols.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/uri/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/uri/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/uri`

