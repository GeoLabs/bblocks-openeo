This Building Block proposes a schema representation of the OpenEO process [`is_nan`](https://processes.openeo.org/#is_nan) — *Value is not a number*. It models the `arguments` object of a process graph node invoking `is_nan`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified value `x` carries the special value `NaN` (not a number) as defined by the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935), in which case it returns `true`. Returns `false` otherwise.

## Source

OpenEO Processes specification: [`is_nan`](https://processes.openeo.org/#is_nan) ([openeo-processes/is_nan.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nan.json)).
