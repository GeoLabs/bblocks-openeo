This Building Block proposes a schema representation of the OpenEO process [`tan`](https://processes.openeo.org/#tan) — *Tangent*. It models the `arguments` object of a process graph node invoking `tan`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the tangent of `x`. The tangent is defined to be the sine of x divided by the cosine of x.

Works on radians only.
No-data values are passed through.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, *`tan(pi()/2 + multipliy(pi(), n))`* with `n` being any integer results in ±infinity. -infinity for negative values passed to `tan`, +infinity otherwise. If the processing environment does not supports it, an exception is thrown.

## Source

OpenEO Processes specification: [`tan`](https://processes.openeo.org/#tan) ([openeo-processes/tan.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/tan.json)).
