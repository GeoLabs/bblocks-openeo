
# Mask (Schema)

`ogc.openeo.processes.cubes.mask` *v0.1*

Apply a raster mask

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`mask`](https://processes.openeo.org/#mask) — *Apply a raster mask*. It models the `arguments` object of a process graph node invoking `mask`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a mask to a raster data cube. To apply a polygon as a mask, use `mask_polygon()`.

A mask is a raster data cube for which corresponding pixels among `data` and `mask` are compared and those pixels in `data` are replaced whose pixels in `mask` are non-zero (for numbers) or `true` (for boolean values). The pixel values are replaced with the value specified for `replacement`, which defaults to the no-data value of the raster data cube.

The data cubes have to be compatible except that the horizontal spatial dimensions (axes `x` and `y`) will be aligned implicitly by `resample_cube_spatial()`. `data` is the target data cube for resampling and the default parameters of `resample_cube_spatial()` apply. All other dimensions in the mask must also be available in the raster data cube with the same name, type, reference system, resolution and labels. Dimensions can be missing in the mask with the result that the mask is applied to each label of the dimension in `data` that is missing in the data cube of the mask. The process fails with a `DimensionMismatch` exception if there's an incompatibility found between the raster data cube and the mask.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `mask` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `IncompatibleDataCubes`: The data cube and the mask are incompatible, e.g. because of different dimensions or labels.

## Source

OpenEO Processes specification: [`mask`](https://processes.openeo.org/#mask) ([openeo-processes/mask.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mask.json)).

## Examples

### Example 1
Calling `mask` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "mask": {
    "from_parameter": "mask"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Apply a raster mask
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  mask:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  replacement:
    type:
    - number
    - boolean
    - string
    - 'null'
required:
- data
- mask

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/mask/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/mask/schema.yaml)

## Sources

* [OpenEO Processes — mask](https://processes.openeo.org/#mask)
* [Open-EO/openeo-processes — mask.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/mask.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/mask`

