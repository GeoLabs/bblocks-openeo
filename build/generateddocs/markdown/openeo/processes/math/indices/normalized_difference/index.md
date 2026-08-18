
# Normalized difference (Schema)

`ogc.openeo.processes.math.indices.normalized_difference` *v0.1*

Normalized difference

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`normalized_difference`](https://processes.openeo.org/#normalized_difference) — *Normalized difference*. It models the `arguments` object of a process graph node invoking `normalized_difference`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the normalized difference for two bands. The normalized difference is computed as *`(x - y) / (x + y)`*.

This process could be used for a number of remote sensing indices such as:

* [NDVI](https://eos.com/ndvi/): `x` = NIR band, `y` = red band
* [NDWI](https://eos.com/ndwi/): `x` = NIR band, `y` = SWIR band
* [NDSI](https://eos.com/ndsi/): `x` = green band, `y` = SWIR band

Some back-ends may have native processes such as `ndvi()` available for convenience.

## Source

OpenEO Processes specification: [`normalized_difference`](https://processes.openeo.org/#normalized_difference) ([openeo-processes/normalized_difference.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/normalized_difference.json)).

## Examples

### NDVI-style normalized difference
Calling `normalized_difference` with these arguments returns `0.7142857142857143`.

For example, `x` = NIR reflectance and `y` = red reflectance gives NDVI.
#### json
```json
{
  "x": 0.6,
  "y": 0.1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Normalized difference
type: object
properties:
  x:
    type: number
  y:
    type: number
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/indices/normalized_difference/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/indices/normalized_difference/schema.yaml)

## Sources

* [OpenEO Processes — normalized_difference](https://processes.openeo.org/#normalized_difference)
* [Open-EO/openeo-processes — normalized_difference.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/normalized_difference.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/indices/normalized_difference`

