This Building Block proposes a schema representation of the OpenEO process [`date_between`](https://processes.openeo.org/#date_between) — *Between comparison for dates and times*. It models the `arguments` object of a process graph node invoking `date_between`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

By default, this process checks whether `x` is later than or equal to `min` and before or equal to `max`.

If `exclude_max` is set to `true` the upper bound is excluded so that the process checks whether `x` is later than or equal to `min` and before `max`.

Lower and upper bounds are not allowed to be swapped. So `min` MUST be before or equal to `max` or otherwise the process always returns `false`.

## Source

OpenEO Processes specification: [`date_between`](https://processes.openeo.org/#date_between) ([openeo-processes/date_between.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_between.json)).
