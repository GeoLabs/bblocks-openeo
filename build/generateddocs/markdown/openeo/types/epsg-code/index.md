
# OpenEO type: EPSG Code (Schema)

`ogc.openeo.types.epsg-code` *v0.1*

A coordinate reference system identified by its EPSG code.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `epsg-code`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Specifies details about cartographic projections as [EPSG](http://www.epsg.org) code.

## Examples

### Example 1
An example value for this subtype: `3857`.

### Example value
The EPSG code for WGS 84. For example, `4326`.
## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: integer
subtype: epsg-code
title: EPSG Code
description: Specifies details about cartographic projections as [EPSG](http://www.epsg.org)
  code.
minimum: 1000

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/epsg-code/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/epsg-code/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/epsg-code`

