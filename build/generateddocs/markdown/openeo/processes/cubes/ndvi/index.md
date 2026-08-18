
# Ndvi (Schema)

`ogc.openeo.processes.cubes.ndvi` *v0.1*

Normalized Difference Vegetation Index

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`ndvi`](https://processes.openeo.org/#ndvi) — *Normalized Difference Vegetation Index*. It models the `arguments` object of a process graph node invoking `ndvi`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the Normalized Difference Vegetation Index (NDVI). The NDVI is computed as *`(nir - red) / (nir + red)`*.

The `data` parameter expects a raster data cube with a dimension of type `bands` or a `DimensionAmbiguous` exception is thrown otherwise. By default, the dimension must have at least two bands with the common names `red` and `nir` assigned. Otherwise, the user has to specify the parameters `nir` and `red`. If neither is the case, either the exception `NirBandAmbiguous` or `RedBandAmbiguous` is thrown. The common names for each band are specified in the collection's band metadata and are *not* equal to the band names.

By default, the dimension of type `bands` is dropped by this process. To keep the dimension specify a new band name in the parameter `target_band`. This adds a new dimension label with the specified name to the dimension, which can be used to access the computed values. If a band with the specified name exists, a `BandExists` is thrown.

This process is very similar to the process `normalized_difference()`, but determines the bands automatically based on the common names (`red`/`nir`) specified in the metadata.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `NirBandAmbiguous`: The NIR band can't be resolved, please specify the specific NIR band name.
- `RedBandAmbiguous`: The red band can't be resolved, please specify the specific red band name.
- `DimensionAmbiguous`: dimension of type `bands` is not available or is ambiguous..
- `BandExists`: A band with the specified target name exists.

## Source

OpenEO Processes specification: [`ndvi`](https://processes.openeo.org/#ndvi) ([openeo-processes/ndvi.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ndvi.json)).

## Examples

### Example 1
Calling `ndvi` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint. Uses the `nir`/`red` defaults (band common names `nir` and `red`), so no explicit band names are needed here.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Normalized Difference Vegetation Index
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  nir:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.yaml
  red:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.yaml
  target_band:
    anyOf:
    - type: string
      pattern: ^\w+$
    - type: 'null'
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/ndvi/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/ndvi/schema.yaml)

## Sources

* [OpenEO Processes — ndvi](https://processes.openeo.org/#ndvi)
* [Open-EO/openeo-processes — ndvi.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ndvi.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/ndvi`

