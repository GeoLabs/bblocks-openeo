This Building Block proposes a schema representation of the OpenEO process [`aggregate_spatial`](https://processes.openeo.org/#aggregate_spatial) — *Zonal statistics for geometries*. It models the `arguments` object of a process graph node invoking `aggregate_spatial`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Aggregates statistics for one or more geometries (e.g. zonal statistics for polygons) over the spatial dimensions. The given data cube can have multiple additional dimensions and for all these dimensions results will be computed individually.

An 'unbounded' aggregation over the full extent of the horizontal spatial dimensions can be computed with the process `reduce_spatial()`.

This process passes a list of values to the reducer. The list of values has an undefined order, therefore processes such as `last()` and `first()` that depend on the order of the values will lead to unpredictable results.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: An array with elements of any type.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the vector data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `geometries` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `TargetDimensionExists`: A dimension with the specified target dimension name already exists.

## Source

OpenEO Processes specification: [`aggregate_spatial`](https://processes.openeo.org/#aggregate_spatial) ([openeo-processes/aggregate_spatial.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_spatial.json)).
