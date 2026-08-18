
# OpenEO type: UDF Runtime version (Schema)

`ogc.openeo.types.udf-runtime-version` *v0.1*

The version identifier of a UDF runtime.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `udf-runtime-version`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

The version of the UDF runtime you want to run the given UDF source code with.

## Examples

### Example value
A UDF runtime version identifier.
#### json
```json
"3.10"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: udf-runtime-version
title: UDF Runtime version
description: The version of the UDF runtime you want to run the given UDF source code
  with.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-runtime-version/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-runtime-version/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/udf-runtime-version`

