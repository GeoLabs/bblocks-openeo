
# Apply kernel (Schema)

`ogc.openeo.processes.cubes.apply_kernel` *v0.1*

Apply a spatial convolution with a kernel

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`apply_kernel`](https://processes.openeo.org/#apply_kernel) — *Apply a spatial convolution with a kernel*. It models the `arguments` object of a process graph node invoking `apply_kernel`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a 2D convolution (i.e. a focal operation with a weighted kernel) on the horizontal spatial dimensions (axes `x` and `y`) of a raster data cube.

Each value in the kernel is multiplied with the corresponding pixel value and all products are summed up afterwards. The sum is then multiplied with the factor.

The process can't handle non-numerical or infinite numerical values in the data cube. Boolean values are converted to integers (`false` = 0, `true` = 1), but all other non-numerical, NaN, no-data, or infinite values are replaced with zeroes by default (see parameter `replace_invalid`).

For cases requiring more generic focal operations or non-numerical values, see `apply_neighborhood()`.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `KernelDimensionsUneven`: Each dimension of the kernel must have an uneven number of elements.

## Source

OpenEO Processes specification: [`apply_kernel`](https://processes.openeo.org/#apply_kernel) ([openeo-processes/apply_kernel.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_kernel.json)).

## Examples

### Example 1
Calling `apply_kernel` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "kernel": [
    [
      1,
      1,
      1
    ],
    [
      1,
      -8,
      1
    ],
    [
      1,
      1,
      1
    ]
  ],
  "factor": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Apply a spatial convolution with a kernel
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  kernel:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/kernel/schema.yaml
  factor:
    type: number
  border:
    anyOf:
    - type: string
      enum:
      - replicate
      - reflect
      - reflect_pixel
      - wrap
    - type: number
  replace_invalid:
    type: number
required:
- data
- kernel

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply_kernel/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/apply_kernel/schema.yaml)

## Sources

* [OpenEO Processes — apply_kernel](https://processes.openeo.org/#apply_kernel)
* [Open-EO/openeo-processes — apply_kernel.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_kernel.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/apply_kernel`

