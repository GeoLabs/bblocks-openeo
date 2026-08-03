This Building Block proposes a schema representation of the OpenEO process [`is_valid`](https://processes.openeo.org/#is_valid) — *Value is valid data*. It models the `arguments` object of a process graph node invoking `is_valid`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified value `x` is valid. The following values are considered valid:

* Any finite numerical value (integers and floating-point numbers). The definition of finite numbers follows the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935) and excludes the special value `NaN` (not a number).
* Any other value that is not a no-data value according to `is_nodata()`. Thus all arrays, objects and strings are valid, regardless of their content.

## Source

OpenEO Processes specification: [`is_valid`](https://processes.openeo.org/#is_valid) ([openeo-processes/is_valid.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_valid.json)).
