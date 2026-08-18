
# OpenEO type: Multiple temporal intervals (Schema)

`ogc.openeo.types.temporal-intervals` *v0.1*

An array of (possibly overlapping) temporal intervals.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `temporal-intervals`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Left-closed temporal intervals, which are allowed to overlap. Formatted as an array of two-element arrays, each being an array with subtype `temporal-interval`.

## Examples

### Example 1
An example value for this subtype.
#### json
```json
[
  [
    "2015-01-01",
    "2016-01-01"
  ],
  [
    "2016-01-01",
    "2017-01-01"
  ],
  [
    "2017-01-01",
    "2018-01-01"
  ]
]
```


### Example 2
An example value for this subtype.
#### json
```json
[
  [
    "00:00:00",
    "12:00:00"
  ],
  [
    "12:00:00",
    null
  ]
]
```


### Example value
Two consecutive half-year intervals.
#### json
```json
[
  [
    "2020-01-01",
    "2020-07-01"
  ],
  [
    "2020-07-01",
    "2021-01-01"
  ]
]
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: array
subtype: temporal-intervals
title: Multiple temporal intervals
description: Left-closed temporal intervals, which are allowed to overlap. Formatted
  as an array of two-element arrays, each being an array with subtype `temporal-interval`.
items:
  $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-interval/schema.yaml
minItems: 1

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-intervals/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-intervals/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/temporal-intervals`

