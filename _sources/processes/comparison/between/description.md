This Building Block proposes a schema representation of the OpenEO process [`between`](https://processes.openeo.org/#between) — *Between comparison*. It models the `arguments` object of a process graph node invoking `between`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

By default, this process checks whether `x` is greater than or equal to `min` and lower than or equal to `max`, which is the same as computing `and(gte(x, min), lte(x, max))`. Therefore, all definitions from `and()`, `gte()` and `lte()` apply here as well.

If `exclude_max` is set to `true` the upper bound is excluded so that the process checks whether `x` is greater than or equal to `min` and lower than `max`. In this case, the process works the same as computing `and(gte(x, min), lt(x, max))`.

Lower and upper bounds are not allowed to be swapped. So `min` MUST be lower than or equal to `max` or otherwise the process always returns `false`.

## Source

OpenEO Processes specification: [`between`](https://processes.openeo.org/#between) ([openeo-processes/between.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/between.json)).
