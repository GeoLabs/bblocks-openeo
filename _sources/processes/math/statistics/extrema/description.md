This Building Block proposes a schema representation of the OpenEO process [`extrema`](https://processes.openeo.org/#extrema) — *Minimum and maximum values*. It models the `arguments` object of a process graph node invoking `extrema`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Two element array containing the minimum and the maximum values of `data`.

This process is basically an alias for calling both `min()` and `max()`, but may be implemented more performant by back-ends as it only needs to iterate over the data once instead of twice.

## Source

OpenEO Processes specification: [`extrema`](https://processes.openeo.org/#extrema) ([openeo-processes/extrema.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/extrema.json)).
