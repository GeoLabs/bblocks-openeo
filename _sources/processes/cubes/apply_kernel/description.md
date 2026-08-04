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
