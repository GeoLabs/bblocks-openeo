This Building Block proposes a schema representation of the OpenEO process [`aggregate_temporal`](https://processes.openeo.org/#aggregate_temporal) — *Temporal aggregations*. It models the `arguments` object of a process graph node invoking `aggregate_temporal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes a temporal aggregation based on an array of temporal intervals.

For common regular calendar hierarchies such as year, month, week or seasons `aggregate_temporal_period()` can be used. Other calendar hierarchies must be transformed into specific intervals by the clients.

For each interval, all data along the dimension will be passed through the reducer.

The computed values will be projected to the labels. If no labels are specified, the start of the temporal interval will be used as label for the corresponding values. In case of a conflict (i.e. the user-specified values for the start times of the temporal intervals are not distinct), the user-defined labels must be specified in the parameter `labels` as otherwise a `DistinctDimensionLabelsRequired` exception would be thrown. The number of user-defined labels and the number of intervals need to be equal.

If the dimension is not set or is set to `null`, the data cube is expected to only have one temporal dimension.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: A labeled array with elements of any type. If there's no data for the interval, the array is empty.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `TooManyDimensions`: The data cube contains multiple temporal dimensions. The parameter `dimension` must be specified.
- `DimensionNotAvailable`: A dimension with the specified name does not exist or no temporal dimension is available.
- `DistinctDimensionLabelsRequired`: The dimension labels have duplicate values. Distinct labels must be specified.
- `TemporalExtentEmpty`: At least one of the intervals is empty. The second instant in time must always be greater/later than the first instant.

## Source

OpenEO Processes specification: [`aggregate_temporal`](https://processes.openeo.org/#aggregate_temporal) ([openeo-processes/aggregate_temporal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_temporal.json)).
