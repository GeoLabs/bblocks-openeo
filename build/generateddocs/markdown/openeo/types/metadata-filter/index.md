
# OpenEO type: Filters (Schema)

`ogc.openeo.types.metadata-filter` *v0.1*

A set of metadata property filters, each expressed as a callback (child process).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `metadata-filter`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A list of filters to check against. Specify key-value-pairs with the key being the name of the metadata property name and the value being a user-defined process evaluated against the metadata values.

## Examples

### Example value
Filters collections/items to those with less than 50% cloud cover.
#### json
```json
{
  "eo:cloud_cover": {
    "process_graph": {
      "lt1": {
        "process_id": "lt",
        "arguments": {
          "x": {
            "from_parameter": "value"
          },
          "y": 50
        },
        "result": true
      }
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: metadata-filter
title: Filters
description: A list of filters to check against. Specify key-value-pairs with the
  key being the name of the metadata property name and the value being a user-defined
  process evaluated against the metadata values.
additionalProperties:
  $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/metadata-filter/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/metadata-filter/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/metadata-filter`

