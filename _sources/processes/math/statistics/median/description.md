This Building Block proposes a schema representation of the OpenEO process [`median`](https://processes.openeo.org/#median) — *Statistical median*. It models the `arguments` object of a process graph node invoking `median`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The statistical median of an array of numbers is the value separating the higher half from the lower half of the data.

An array with solely no-data values returns the no-data value (or `null`).

**Remarks:**

* For symmetric arrays, the result is equal to the `mean()`.
* The median can also be calculated by computing the `quantiles()` with a probability of *0.5*.

## Source

OpenEO Processes specification: [`median`](https://processes.openeo.org/#median) ([openeo-processes/median.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/median.json)).
