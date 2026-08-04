This Building Block proposes a schema representation of the OpenEO process [`apply_neighborhood`](https://processes.openeo.org/#apply_neighborhood) — *Apply a process to pixels in a n-dimensional neighborhood*. It models the `arguments` object of a process graph node invoking `apply_neighborhood`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Applies a focal process to a data cube.

A focal process is a process that works on a 'neighborhood' of pixels. The neighborhood can extend into multiple dimensions, this extent is specified by the `size` argument. It is not only (part of) the size of the input window, but also the size of the output for a given position of the sliding window. The sliding window moves with multiples of `size`.

An overlap can be specified so that neighborhoods can have overlapping boundaries. This allows for continuity of the output. The overlap region must be included in the data cube or array returned by `process`, but any changed values will be ignored. The missing overlap at the borders of the original data cube is made available as no-data values in the sub-data cubes.

The neighborhood size should be kept small enough, to avoid running beyond computational resources, but a too-small size will result in a larger number of process invocations, which may slow down processing. Window sizes for spatial dimensions typically range from 64 to 512 pixels, while overlaps of 8 to 32 pixels are common.

For the special case of 2D convolution, it is recommended to use `apply_kernel()`.

## Callback (child process) signature

The child process passed as `process` is called with the following named parameters:

- `data`: The input data, which is a subset of the data cube as specified in `size` and `overlap`. If the given size and overlap result in a one-dimensional data cube it is converted to a labeled array.
- `context` (optional): Additional data passed by the user.

It must return: An array or data cube with the newly computed values. The data type and dimensionality must correspond to the input data.

* Data cubes must have the same dimensions and the dimension properties (name, type, labels, reference system and resolution) must remain unchanged. Otherwise, a `DataCubePropertiesImmutable` exception will be thrown.
* Arrays can be returned with or without labels.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.
- `DataCubePropertiesImmutable`: The dimension properties (name, type, labels, reference system and resolution) must remain unchanged.

## Source

OpenEO Processes specification: [`apply_neighborhood`](https://processes.openeo.org/#apply_neighborhood) ([openeo-processes/apply_neighborhood.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/apply_neighborhood.json)).
