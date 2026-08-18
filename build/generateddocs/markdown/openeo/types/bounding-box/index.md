
# OpenEO type: Bounding Box (Schema)

`ogc.openeo.types.bounding-box` *v0.1*

A spatial bounding box given as west/south/east/north extents and an optional CRS.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `bounding-box`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A bounding box with the required fields `west`, `south`, `east`, `north` and optionally `base`, `height`, `crs`. The `crs` is a EPSG code or a WKT2:2018 string.

## Examples

### Example value
A bounding box around Vienna, Austria, in EPSG:4326.
#### json
```json
{
  "west": 16.06,
  "south": 48.06,
  "east": 16.65,
  "north": 48.31,
  "crs": 4326
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: bounding-box
title: Bounding Box
description: A bounding box with the required fields `west`, `south`, `east`, `north`
  and optionally `base`, `height`, `crs`. The `crs` is a EPSG code or a WKT2:2018
  string.
required:
- west
- south
- east
- north
properties:
  west:
    description: West (lower left corner, coordinate axis 1).
    type: number
  south:
    description: South (lower left corner, coordinate axis 2).
    type: number
  east:
    description: East (upper right corner, coordinate axis 1).
    type: number
  north:
    description: North (upper right corner, coordinate axis 2).
    type: number
  base:
    description: Base (optional, lower left corner, coordinate axis 3).
    type:
    - number
    - 'null'
    default: null
  height:
    description: Height (optional, upper right corner, coordinate axis 3).
    type:
    - number
    - 'null'
    default: null
  crs:
    description: Coordinate reference system of the extent, specified as [EPSG code](https://spatialreference.org/ref/epsg/)
      or [WKT2 CRS string](http://docs.opengeospatial.org/is/18-010r7/18-010r7.html).
      Defaults to `4326` (EPSG code 4326) unless the client explicitly requests a
      different coordinate reference system.
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/epsg-code/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/wkt2-definition/schema.yaml
    default: 4326

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/bounding-box/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/bounding-box/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/bounding-box`

