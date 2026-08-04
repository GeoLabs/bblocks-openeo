This Building Block proposes a schema representation of the OpenEO process [`aggregate_temporal_period`](https://processes.openeo.org/#aggregate_temporal_period) — *Temporal aggregations based on calendar hierarchies*. It models the `arguments` object of a process graph node invoking `aggregate_temporal_period`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes a temporal aggregation based on calendar hierarchies such as years, months or seasons. For other calendar hierarchies `aggregate_temporal()` can be used.

For each interval, all data along the dimension will be passed through the reducer.

If the dimension is not set or is set to `null`, the data cube is expected to only have one temporal dimension.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: A labeled array with elements of any type. If there's no data for the period, the array is empty.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `TooManyDimensions`: The data cube contains multiple temporal dimensions. The parameter `dimension` must be specified.
- `DimensionNotAvailable`: A dimension with the specified name does not exist or no temporal dimension is available.

## Source

OpenEO Processes specification: [`aggregate_temporal_period`](https://processes.openeo.org/#aggregate_temporal_period) ([openeo-processes/aggregate_temporal_period.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_temporal_period.json)).
