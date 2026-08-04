This Building Block proposes a schema representation of the OpenEO process [`run_udf`](https://processes.openeo.org/#run_udf) — *Run a UDF*. It models the `arguments` object of a process graph node invoking `run_udf`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Runs a UDF in one of the supported runtime environments.

The process can either:

1. load and run a UDF stored in a file on the server-side workspace of the authenticated user. The path to the UDF file must be relative to the root directory of the user's workspace.
2. fetch and run a remotely stored and published UDF by absolute URI.
3. run the source code specified inline as string.

The loaded UDF can be executed in several processes such as `aggregate_spatial()`, `apply()`, `apply_dimension()` and `reduce_dimension()`. The user must ensure that the data is provided in a way that the UDF code can make sense of it.

## Exceptions

- `InvalidRuntime`: The specified UDF runtime is not supported.
- `InvalidVersion`: The specified UDF runtime version is not supported.
- `FileNotFound`: The specified file does not exist.

## Source

OpenEO Processes specification: [`run_udf`](https://processes.openeo.org/#run_udf) ([openeo-processes/run_udf.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/run_udf.json)).
