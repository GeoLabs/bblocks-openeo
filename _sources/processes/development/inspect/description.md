This Building Block proposes a schema representation of the OpenEO process [`inspect`](https://processes.openeo.org/#inspect) — *Add information to the logs*. It models the `arguments` object of a process graph node invoking `inspect`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

This process can be used to add runtime information to the logs, e.g. for debugging purposes. This process should be used with caution and it is recommended to remove the process in production workflows. For example, logging each value or array individually in a process such as `apply()` or `reduce_dimension()` could lead to a (too) large number of log entries. Several data structures (e.g. data cubes) are too large to log and will only return summaries of their contents.

The data provided in the parameter `data` is returned without changes.

## Source

OpenEO Processes specification: [`inspect`](https://processes.openeo.org/#inspect) ([openeo-processes/inspect.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/inspect.json)).
