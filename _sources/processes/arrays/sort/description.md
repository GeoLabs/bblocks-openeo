This Building Block proposes a schema representation of the OpenEO process [`sort`](https://processes.openeo.org/#sort) — *Sort data*. It models the `arguments` object of a process graph node invoking `sort`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Sorts an array into ascending (default) or descending order.

**Remarks:**

* The ordering of ties is implementation-dependent.
* Temporal strings can *not* be compared based on their string representation due to the time zone/time-offset representations.

## Source

OpenEO Processes specification: [`sort`](https://processes.openeo.org/#sort) ([openeo-processes/sort.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sort.json)).
