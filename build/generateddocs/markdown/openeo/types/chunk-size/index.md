
# OpenEO type: Chunk Size (Schema)

`ogc.openeo.types.chunk-size` *v0.1*

A per-dimension chunk size specification for tiling/processing hints.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `chunk-size`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

The chunk size per dimension given. This object maps the dimension names given as key to chunks given as either a physical measure or pixels. If not given or `null`, no chunking is applied.

## Examples

### Example value
A 256-pixel chunk size for the x dimension.
#### json
```json
{
  "dimension": "x",
  "value": 256
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: chunk-size
title: Chunk Size
description: The chunk size per dimension given. This object maps the dimension names
  given as key to chunks given as either a physical measure or pixels. If not given
  or `null`, no chunking is applied.
required:
- dimension
- value
properties:
  dimension:
    type: string
  value:
    default: null
    anyOf:
    - type: 'null'
    - type: number
      minimum: 0
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/duration/schema.yaml
  unit:
    type: string
    description: The unit the values are given in. If no unit is given, uses the unit
      specified for the dimension or otherwise the default unit of the reference system.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/chunk-size/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/chunk-size/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/chunk-size`

