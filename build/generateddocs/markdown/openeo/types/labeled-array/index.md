
# OpenEO type: Array with labels (Schema)

`ogc.openeo.types.labeled-array` *v0.1*

An ordered, associative array: a list of values with a label attached to each value.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `labeled-array`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

An associative, ordered list of key-value pairs. Basically an array, which additionally has labels for each value. Labels can be numbers or (temporal) strings.

**Important:** Due to the lack of such a data type in JSON, the schema for the items is not formally specified yet and a placeholder.

## Examples

### Example value
An array; when labeled, each value would carry an associated label.
#### json
```json
[
  1,
  2,
  3
]
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: array
subtype: labeled-array
title: Array with labels
description: 'An associative, ordered list of key-value pairs. Basically an array,
  which additionally has labels for each value. Labels can be numbers or (temporal)
  strings.


  **Important:** Due to the lack of such a data type in JSON, the schema for the items
  is not formally specified yet and a placeholder.'
items:
  description: Any data type.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/labeled-array/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/labeled-array/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/labeled-array`

