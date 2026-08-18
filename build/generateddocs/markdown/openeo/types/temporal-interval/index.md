
# OpenEO type: Single temporal interval (Schema)

`ogc.openeo.types.temporal-interval` *v0.1*

A single left-closed temporal interval, as a two-element array [start, end].

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `temporal-interval`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Left-closed temporal interval, represented as two-element array with the following elements:

1. The first element is the start of the temporal interval. The specified time instant is **included** in the interval.
2. The second element is the end of the temporal interval. The specified time instant is **excluded** from the interval.

The second element must always be greater/later than the first element. Otherwise, an exception is thrown.

The specified temporal strings follow [RFC 3339](https://www.rfc-editor.org/rfc/rfc3339.html). Also supports unbounded intervals by setting one of the boundaries to `null`, but never both.

## Examples

### Example 1
An example value for this subtype.
#### json
```json
[
  "2015-01-01T00:00:00Z",
  "2016-01-01T00:00:00Z"
]
```


### Example 2
An example value for this subtype.
#### json
```json
[
  "2015-01-01",
  "2016-01-01"
]
```


### Example value
A left-closed interval covering the year 2020.
#### json
```json
[
  "2020-01-01",
  "2021-01-01"
]
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: array
subtype: temporal-interval
title: Single temporal interval
description: 'Left-closed temporal interval, represented as two-element array with
  the following elements:


  1. The first element is the start of the temporal interval. The specified time instant
  is **included** in the interval.

  2. The second element is the end of the temporal interval. The specified time instant
  is **excluded** from the interval.


  The second element must always be greater/later than the first element. Otherwise,
  an exception is thrown.


  The specified temporal strings follow [RFC 3339](https://www.rfc-editor.org/rfc/rfc3339.html).
  Also supports unbounded intervals by setting one of the boundaries to `null`, but
  never both.'
uniqueItems: true
minItems: 2
maxItems: 2
items:
  description: Processes and implementations may choose to only implement a subset
    of the subtypes specified here. Clients must check what back-ends / processes
    actually support.
  anyOf:
  - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
  - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
  - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.yaml
  - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/year/schema.yaml
  - type: 'null'

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-interval/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-interval/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/temporal-interval`

