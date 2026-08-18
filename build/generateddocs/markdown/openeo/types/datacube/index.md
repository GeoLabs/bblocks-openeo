
# OpenEO type: Data Cube (Schema)

`ogc.openeo.types.datacube` *v0.1*

A data cube with an arbitrary number of dimensions, without a required dimension typing.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `datacube`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A data cube that consists of an arbitrary number of dimensions and doesn't require any dimension type specifically.

## Examples

### Example value
A data cube reference. In an actual process graph, cube-valued arguments are normally supplied as node/parameter references (`from_node`/`from_parameter`, defined by the OpenEO API rather than this processes schema); this schema only constrains the value to be an object.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: datacube
title: Data Cube
description: A data cube that consists of an arbitrary number of dimensions and doesn't
  require any dimension type specifically.

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/datacube`

