
# OpenEO type: WKT2 definition (Schema)

`ogc.openeo.types.wkt2-definition` *v0.1*

A coordinate reference system given as a WKT2 string.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `wkt2-definition`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Specifies details about cartographic projections as WKT2 string. Refers to the latest WKT2 version (currently [WKT2:2018](http://docs.opengeospatial.org/is/18-010r7/18-010r7.html) / ISO 19162:2018) unless otherwise stated by the process.

## Examples

### Example value
A (truncated) WKT2 CRS definition.
#### json
```json
"GEOGCRS[\"WGS 84\", ...]"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: wkt2-definition
title: WKT2 definition
description: Specifies details about cartographic projections as WKT2 string. Refers
  to the latest WKT2 version (currently [WKT2:2018](http://docs.opengeospatial.org/is/18-010r7/18-010r7.html)
  / ISO 19162:2018) unless otherwise stated by the process.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/wkt2-definition/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/wkt2-definition/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/wkt2-definition`

