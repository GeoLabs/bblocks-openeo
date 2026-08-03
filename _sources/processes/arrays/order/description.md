This Building Block proposes a schema representation of the OpenEO process [`order`](https://processes.openeo.org/#order) — *Get the order of array elements*. It models the `arguments` object of a process graph node invoking `order`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the ranked (sorted) element positions in the original list (i.e., a permutation), either in ascending or descending order. The process `rearrange()` allows sorting the data based on the computed permutation.

**Remarks:**

* The positions in the result are zero-based.
* The ordering of ties is implementation-dependent.
* Temporal strings can *not* be compared based on their string representation due to the time zone/time-offset representations.

## Source

OpenEO Processes specification: [`order`](https://processes.openeo.org/#order) ([openeo-processes/order.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/order.json)).
