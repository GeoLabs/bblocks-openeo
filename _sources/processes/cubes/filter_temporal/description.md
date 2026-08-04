This Building Block proposes a schema representation of the OpenEO process [`filter_temporal`](https://processes.openeo.org/#filter_temporal) — *Temporal filter based on temporal intervals*. It models the `arguments` object of a process graph node invoking `filter_temporal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Limits the data cube to the specified interval of dates and/or times.

More precisely, the filter checks whether each of the temporal dimension labels is greater than or equal to the lower boundary (start date/time) and less than the value of the upper boundary (end date/time). This corresponds to a left-closed interval, which contains the lower boundary but not the upper boundary.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.
- `TemporalExtentEmpty`: The temporal extent is empty. The second instant in time must always be greater/later than the first instant in time.

## Source

OpenEO Processes specification: [`filter_temporal`](https://processes.openeo.org/#filter_temporal) ([openeo-processes/filter_temporal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_temporal.json)).
