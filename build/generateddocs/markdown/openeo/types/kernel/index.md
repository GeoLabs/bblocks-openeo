
# OpenEO type: Image Kernel (Schema)

`ogc.openeo.types.kernel` *v0.1*

A two-dimensional numeric array used as a convolution kernel.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `kernel`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A two-dimensional array of numbers to be used as kernel for the image operation.

## Examples

### Example value
A 3x3 Laplacian edge-detection kernel.
#### json
```json
[
  [
    1,
    1,
    1
  ],
  [
    1,
    -8,
    1
  ],
  [
    1,
    1,
    1
  ]
]
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: array
subtype: kernel
title: Image Kernel
description: A two-dimensional array of numbers to be used as kernel for the image
  operation.
items:
  type: array
  items:
    type: number

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/kernel/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/kernel/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/kernel`

