This Building Block proposes a schema representation of the OpenEO process [`arcsin`](https://processes.openeo.org/#arcsin) — *Inverse sine*. It models the `arguments` object of a process graph node invoking `arcsin`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the arc sine of `x`. The arc sine is the inverse function of the sine so that *`arcsin(sin(x)) = x`*.

Works on radians only.
No-data values are passed through. `NaN` is returned for values < -1 and > 1.

## Source

OpenEO Processes specification: [`arcsin`](https://processes.openeo.org/#arcsin) ([openeo-processes/arcsin.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcsin.json)).
