This Building Block proposes a schema representation of the OpenEO process [`sgn`](https://processes.openeo.org/#sgn) — *Signum*. It models the `arguments` object of a process graph node invoking `sgn`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The signum (also known as *sign*) of `x` is defined as:

* *1* if *x > 0*
* *0* if *x = 0*
* *-1* if *x < 0*

No-data values are passed through.

## Source

OpenEO Processes specification: [`sgn`](https://processes.openeo.org/#sgn) ([openeo-processes/sgn.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/sgn.json)).
