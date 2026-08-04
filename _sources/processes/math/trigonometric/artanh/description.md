This Building Block proposes a schema representation of the OpenEO process [`artanh`](https://processes.openeo.org/#artanh) — *Inverse hyperbolic tangent*. It models the `arguments` object of a process graph node invoking `artanh`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the inverse hyperbolic tangent of `x`. It is the inverse function of the hyperbolic tangent so that *`artanh(tanh(x)) = x`*.

No-data values are passed through. `NaN` is returned for values outside of the allowed range. The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it. Therefore, `x` = 1 results in +infinity and `x` = 0 results in -infinity. Otherwise, an exception is thrown.

## Source

OpenEO Processes specification: [`artanh`](https://processes.openeo.org/#artanh) ([openeo-processes/artanh.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/artanh.json)).
