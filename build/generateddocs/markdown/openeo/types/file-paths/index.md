
# OpenEO type: Multiple File paths (Schema)

`ogc.openeo.types.file-paths` *v0.1*

An array of relative paths to user-uploaded files.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `file-paths`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

An array with relative paths to user-uploaded files. Clients should assist to generate a list of files for folders.

## Examples

### Example value
Two relative paths to uploaded files.
#### json
```json
[
  "data/input1.tif",
  "data/input2.tif"
]
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: array
subtype: file-paths
title: Multiple File paths
description: An array with relative paths to user-uploaded files. Clients should assist
  to generate a list of files for folders.
items:
  $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/file-path/schema.yaml

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/file-paths/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/file-paths/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/file-paths`

