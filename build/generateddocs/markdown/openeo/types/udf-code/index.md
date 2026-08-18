
# OpenEO type: UDF source code (Schema)

`ogc.openeo.types.udf-code` *v0.1*

The multi-line source code of a user-defined function (UDF).

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `udf-code`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

The multi-line source code of a user-defined function (UDF), must contain a newline/line-break.

## Examples

### Example value
A minimal Python UDF that doubles the input.
#### json
```json
"import numpy as np\n\ndef apply(data):\n    return data * 2\n"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: udf-code
title: UDF source code
description: The multi-line source code of a user-defined function (UDF), must contain
  a newline/line-break.
pattern: "(\r\n|\r|\n)"

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-code/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-code/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/udf-code`

