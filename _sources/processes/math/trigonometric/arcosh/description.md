This Building Block proposes a schema representation of the OpenEO process [`arcosh`](https://processes.openeo.org/#arcosh) — *Inverse hyperbolic cosine*. It models the `arguments` object of a process graph node invoking `arcosh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the inverse hyperbolic cosine of `x`. It is the inverse function of the hyperbolic cosine so that *`arcosh(cosh(x)) = x`*.

No-data values are passed through. `NaN` is returned for values outside of the allowed range.

## Source

OpenEO Processes specification: [`arcosh`](https://processes.openeo.org/#arcosh) ([openeo-processes/arcosh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/arcosh.json)).
