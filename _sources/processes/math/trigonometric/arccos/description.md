This Building Block proposes a schema representation of the OpenEO process [`arccos`](https://processes.openeo.org/#arccos) — *Inverse cosine*. It models the `arguments` object of a process graph node invoking `arccos`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc cosine of `x`. The arc cosine is the inverse function of the cosine so that *`arccos(cos(x)) = x`*.

Works on radians only.
No-data values are passed through. `NaN` is returned for values < -1 and > 1.

## Source

OpenEO Processes specification: [`arccos`](https://processes.openeo.org/#arccos) ([openeo-processes/arccos.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arccos.json)).
